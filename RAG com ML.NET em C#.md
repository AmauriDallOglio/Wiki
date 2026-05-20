
# Sistema RAG com Treinamento ML.NET

Este projeto implementa um sistema de perguntas e respostas com arquitetura híbrida de RAG (Retrieval-Augmented Generation), voltado para responder perguntas sobre personagens com base em documentos importados.

O fluxo combina três camadas: memória de sessões, modelo treinado com ML.NET e geração contextual com Ollama. Primeiro, o sistema tenta responder pelo histórico já salvo (Sessao) e pelo modelo treinado (ModeloML), priorizando velocidade. Quando não há resposta confiável, ativa o pipeline RAG, que localiza trechos relevantes nos documentos, monta um prompt estruturado e envia ao modelo generativo para produzir a resposta final.

Além disso, a solução possui aprendizado contínuo: cada interação é registrada em sessão e reutilizada no retreinamento periódico do modelo, permitindo melhorar a cobertura de respostas diretas ao longo do tempo e reduzir chamadas desnecessárias ao fluxo completo de RAG.

O objetivo é unir recuperação de contexto, geração de linguagem natural e evolução contínua do conhecimento para entregar respostas cada vez mais rápidas, consistentes e precisas.


<img width="1511" height="844" alt="image" src="https://github.com/user-attachments/assets/d89227d2-9341-41f6-8ced-1894619327da" />

<img width="1511" height="812" alt="image" src="https://github.com/user-attachments/assets/b19c7326-6527-4f53-afc8-512ff9986e25" />
<img width="1507" height="734" alt="image" src="https://github.com/user-attachments/assets/02344ef6-91fc-4414-8ad1-4ed8bbf1dc0c" />

---

<img width="1849" height="829" alt="image" src="https://github.com/user-attachments/assets/ef9d3a3b-3de4-4884-adc1-6018ec7f5b6a" />

---

<img width="1906" height="849" alt="image" src="https://github.com/user-attachments/assets/d318538a-1022-4618-8580-231ec756dc95" />

---

<img width="1844" height="892" alt="image" src="https://github.com/user-attachments/assets/1fac8ebc-2c8a-4921-9fb2-74f1954fabac" />

---

<img width="1855" height="851" alt="image" src="https://github.com/user-attachments/assets/4e8c58dd-c0c5-4997-a2a0-c6db4f355a64" />

---

## Problema encontrado

Com o crescimento da base de dados e do número de consultas, a lentidão não está relacionada apenas ao uso do pipeline RAG, mas também a outros pontos de custo acumulado na aplicação. Hoje, além de executar etapas pesadas de recuperação e geração, o sistema também realiza varreduras extensas de texto, múltiplas operações de string e regex, chamadas externas ao Ollama com tempo limite elevado e persistência de sessão em toda requisição. Em cenários de maior concorrência, isso aumenta o tempo de resposta e o consumo de CPU e I/O.

Outro fator relevante é que parte do fluxo ainda pode bloquear processamento assíncrono e gerar contenção em carga, enquanto componentes de inferência e cache exigem cuidados de escalabilidade para operar bem com muitos acessos simultâneos. Somado a isso, logs detalhados em pontos críticos do fluxo acabam adicionando sobrecarga extra em produção.

Em resumo, o problema atual é multifatorial: o RAG completo em todas as perguntas pesa, mas a degradação de desempenho também vem de decisões de implementação no processamento, acesso a dados, concorrência e integração com o modelo generativo. Isso indica a necessidade de otimização em camadas, priorizando respostas diretas pelo modelo treinado, redução de processamento textual por consulta e melhor estratégia de execução concorrente.

---

##  Solução Proposta: 

<img width="1672" height="941" alt="fluxo_processo_ia_hibrida_v3" src="https://github.com/user-attachments/assets/0ec6ed1f-1ea4-42ff-9d04-1d932e234541" />



### Objetivos:
- Treinar com ML.NET usando histórico
  - Implementado em MachineLearningServico.CriarModelo(...).
  - Fonte de treino: tabela Sessao (_sessaoRepo.ObterTodosAsync).
  - Pipeline ML.NET: FeaturizeText + SdcaMaximumEntropy.
- Armazenar modelo treinado em ModeloML
  - Implementado no mesmo método.
  - Serializa ITransformer para byte[] e salva via _IModeloMLRepositorio.SalvarAsync(modeloML, ...).
- Serviço background a cada 1 hora para retreino
  - Estrutura existe no projeto (Ollama.Api/Configuracao/Tarefas/TarefaModeloML.cs), que é o local correto para esse job.
  - O comportamento esperado é chamar periodicamente CriarModelo(...) (e em seguida manter cache atualizado com CarregaModeloNoCache(...), que já ocorre dentro do fluxo atual).
- Responder direto do modelo sem passar no RAG
  - Implementado em GenerativoPipeline.PerguntarAsync(...):
  - tenta histórico Sessao;
  - depois tenta MachineLearningServico.ObterRespostaModeloMachineLearning(...);
  - se houver resposta com confiança, retorna e não passa no RagServico.

- Resumo para documentação:
  - Sessões alimentam treino ML.NET.
  - Modelo treinado é persistido em ModeloML.
  - Job em background retreina periodicamente (1h).
  - Em runtime, se ModeloML acertar com confiança, resposta é imediata e bypassa RAG/Ollama.

Sessões alimentam treino ML.NET.
Modelo treinado é persistido em ModeloML.
Job em background retreina periodicamente (1h).
Em runtime, se ModeloML acertar com confiança, resposta é imediata e bypassa RAG/Ollama.


---

##  Fluxo com ML.NET

- Usuário envia a pergunta para GenerativoPipeline.PerguntarAsync.
- O sistema consulta primeiro o histórico em Sessao (ObterPorPerguntaAsync).
- Se encontrar resposta no histórico, retorna imediatamente.
- Se não encontrar, tenta previsão no modelo treinado ModeloML via MachineLearningServico.ObterRespostaModeloMachineLearning.
- Se a confiança da previsão for suficiente, retorna a resposta e grava em Sessao.
- Se não houver previsão válida, executa RAG:
  - RagServico.FiltroPalavraChave recupera trechos relevantes.
  - PromptServico.GerarPromptGenerativo monta o prompt com contexto.
  - OllamaServico.ExecutarPromptGeneraticoAsync gera a resposta no Ollama.
- A resposta final é gravada em Sessao.
  - Em ciclos de treinamento futuros, MachineLearningServico.CriarModelo usa os dados de Sessao para gerar/atualizar ModeloML.
Versão curta para documentação:

Pergunta → Histórico Sessao → ModeloML → RAG (RagServico + PromptServico) → Ollama → grava em Sessao → próximo treino do ModeloML.


---

## Componentes Principais
| Componente | Função |
|-------------|--------|
| **GenerativoPipeline**     | Responsável por orquestrar o fluxo completo de resposta (pipeline híbrido). |
| **MachineLearningServico** | Serviço de ML.NET para treinar, carregar e inferir respostas com base nas sessões históricas. |
| **OllamaServico**          | Integração HTTP com servidor Ollama local para geração de texto. |
| **PromptServico**          | Serviço de engenharia de prompt (montagem de instruções para o LLM). |
| **RagServico**             | Serviço de recuperação de contexto (RAG) baseado em palavras-chave/tokens. |

 
1) GenerativoPipeline.cs
- Responsável por orquestrar o fluxo completo de resposta (pipeline híbrido).
- PerguntarAsync(pergunta, cancellationToken)
- Executa a sequência de decisão:
- Busca resposta no histórico de sessões.
- Se não achar, tenta prever resposta com modelo ML.NET.
- Se ainda não achar, usa RAG para buscar trechos relevantes.
- Monta prompt com contexto.
- Chama o Ollama para gerar resposta.
- Salva a sessão (pergunta/resposta) no banco.
- CriarSessao(pergunta, prompt, resposta, cancellationToken)
- Cria e persiste uma sessão de conversa para reaproveitamento futuro.
- O que essa aplicação faz: Atua como “motor central” que combina memória (histórico), ML preditivo e LLM generativo com contexto documental.

2) MachineLearningServico.cs
- Serviço de ML.NET para treinar, carregar e inferir respostas com base nas sessões históricas.
- CarregaModeloNoCache(cancellationToken)
- Carrega do banco o último modelo treinado, desserializa e coloca em cache (PredictionEngine).
- CriarModelo(cancellationToken)
- Lê sessões, transforma em dataset, treina pipeline ML.NET, serializa modelo e salva no banco/cache.
- ObterRespostaModeloMachineLearning(pergunta)
- Faz inferência da resposta e valida por limiar de confiança (nível médio = 0.7).
- Limite(nivel) e enum NivelConfianca
- Define thresholds de confiança para aceitar/rejeitar a previsão.
- O que essa aplicação faz: Reduz chamadas ao LLM ao responder perguntas repetitivas com base no histórico aprendido.

3) OllamaServico.cs
- Integração HTTP com servidor Ollama local para geração de texto.
- ExecutarPromptGeneraticoAsync(pergunta, promptMontado, usuario, cancellationToken)
- Envia prompt contextual ao Ollama (/api/generate), aplica timeout e filtra respostas inválidas.
- ExecutarPromptAsync(promptCompleto, cancellationToken)
- Execução genérica de prompt no Ollama com tratamento de timeout/cancelamento.
- ServidorOllama.
- Método interno que faz POST, lê stream JSON linha a linha e concatena campo response.
- ObterRespostasInvalidas()
- Lista frases que indicam respostas sem valor, para fallback.
- ObterParametrosTemperatura(estilo)
- Define temperature e top_p por estilo (rigoroso/flexível/criativo).
- O que essa aplicação faz: É o gateway de comunicação com o modelo generativo local (Ollama).

4) PromptServico.cs
- Serviço de engenharia de prompt (montagem de instruções para o LLM).
- GerarPromptGenerativo(pergunta, trechosLocalizados, cancellationToken)
- Monta prompt com pergunta + contexto recuperado + regras obrigatórias.
- O que essa aplicação faz: Padroniza e estrutura prompts para aumentar qualidade e consistência das respostas.

5) RagServico.cs
- Serviço de recuperação de contexto (RAG) baseado em palavras-chave/tokens.
- FiltroPalavraChave(pergunta, cancellationToken) - Tokeniza a pergunta, valida presença mínima de tokens no índice (“caça-palavras”), percorre documentos em cache e extrai frases com correspondência.
- Tokenizar(texto) - Normaliza texto, remove stopwords e retorna tokens distintos.
- ignorarPalavras - Conjunto de stopwords em português para limpeza semântica.
- O que essa aplicação faz: Recupera trechos relevantes dos documentos para enriquecer o prompt generativo com contexto factual.


Resumo arquitetural (visão geral)
- GenerativoPipeline coordena tudo.
- MachineLearningServico tenta resposta rápida por histórico aprendido.
- RagServico encontra contexto nos documentos.
- PromptServico monta o prompt final.
- OllamaServico envia ao LLM local e retorna a resposta gerada.

---

## Benefícios
- **Velocidade**: respostas diretas do modelo treinado.  
- **Eficiência**: menor carga sobre o pipeline RAG.  
- **Aprendizado contínuo**: o sistema melhora automaticamente com o tempo.  
- **Escalabilidade**: arquitetura pronta para novos domínios e personagens.

---


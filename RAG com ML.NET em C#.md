
# Sistema RAG com Treinamento ML.NET

Este projeto implementa um sistema baseado em **RAG (Retrieval-Augmented Generation)**, capaz de buscar e gerar respostas contextuais sobre personagens da com base em documentos imortados.  
O objetivo é combinar **busca inteligente**, **geração de texto** e **aprendizado contínuo** para oferecer respostas rápidas e precisas.


<img width="1511" height="844" alt="image" src="https://github.com/user-attachments/assets/d89227d2-9341-41f6-8ced-1894619327da" />

<img width="1511" height="812" alt="image" src="https://github.com/user-attachments/assets/b19c7326-6527-4f53-afc8-512ff9986e25" />
<img width="1507" height="734" alt="image" src="https://github.com/user-attachments/assets/02344ef6-91fc-4414-8ad1-4ed8bbf1dc0c" />

---

## Arquitetura Atual
O fluxo atual funciona da seguinte forma:

1. **Entrada do usuário**  
   O usuário faz uma pergunta sobre um personagem.

2. **Filtragem de contexto**  
   A pergunta é processada pela classe `RagHelper`, que filtra os textos relevantes.

3. **Geração de resposta**  
   Os textos filtrados são enviados ao **Ollama**, que gera a resposta final.

4. **Persistência**  
   A resposta é gravada na tabela `Sessao`, permitindo histórico e reuso.



 
---

## Problema Atual
Com o aumento do volume de dados e consultas, o processo de geração está ficando **lento**, pois cada pergunta passa novamente pelo pipeline completo do RAG.

---

##  Solução Proposta: Classe `MLSessao`
Para otimizar o desempenho, será criada a classe **`MLSessao`**, responsável por **treinar modelos de aprendizado** com base nas respostas já armazenadas na tabela `Sessao`.

### Objetivos:
- Treinar o modelo usando **ML.NET** com os dados históricos.  
- Armazenar o modelo treinado na nova tabela `ModeloML`.  
- Criar um **serviço em background** que roda a cada 1 hora, re‑treinando o modelo com os dados mais recentes.  
- Se uma pergunta tiver correspondência no modelo treinado, retornar a resposta diretamente — **sem passar pelo `RagHelper`**.

---

##  Fluxo com ML.NET
1. Usuário faz uma pergunta.  
2. O sistema verifica se há uma resposta treinada no modelo (`ModeloML`).  
3. Se existir, retorna imediatamente.  
4. Se não existir, passa pelo pipeline RAG (`RagHelper` → `Ollama`).  
5. A resposta é gravada em `Sessao` e usada no próximo ciclo de treinamento.

---

## Componentes Principais
| Componente | Função |
|-------------|--------|
| **RagHelper** | Filtra textos relevantes para o contexto da pergunta. |
| **Ollama** | Modelo generativo local que produz respostas. |
| **Sessao** | Armazena perguntas e respostas históricas. |
| **MLSessao** | Treina e consulta o modelo ML.NET. |
| **ModeloML** | Guarda o modelo treinado e atualizado periodicamente. |
| **Serviço de Treinamento** | Executa a cada 1 hora para atualizar o modelo com novos dados. |

---

## Benefícios Esperados
- **Velocidade**: respostas diretas do modelo treinado.  
- **Eficiência**: menor carga sobre o pipeline RAG.  
- **Aprendizado contínuo**: o sistema melhora automaticamente com o tempo.  
- **Escalabilidade**: arquitetura pronta para novos domínios e personagens.

---

## Próximos Passos
- Implementar a classe `MLSessao` com ML.NET.  
- Criar o serviço de treinamento periódico.  
- Integrar o modelo com o pipeline existente.  
- Monitorar métricas de desempenho e acurácia.

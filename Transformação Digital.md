# Ondas da Transformação Digital

## Por Que Entender as Ondas Antes de Propor IA

Antes de oferecer qualquer solução de IA para um cliente ou empresa, é fundamental compreender em que estágio de maturidade tecnológica ela se encontra. Propor automação inteligente para uma empresa que ainda não domina os fundamentos da nuvem é um erro arquitetural e um dos mais comuns no mercado. As empresas não evoluem de forma linear, e ignorar essa realidade é a principal causa de projetos de IA que fracassam antes mesmo de começar.

As três ondas descritas a seguir não são teoria acadêmica: são padrões observáveis em campo, identificados ao longo de atuação em empresas de planos de saúde, indústria, engenharia civil e tecnologia.


## Onda 1 Digitalização (Anos 2000 até ~2015)

A primeira onda foi a substituição do papel pelos sistemas digitais. Parece distante, mas não é: muitas empresas brasileiras ainda estão saindo dessa fase ou a vivem de forma parcial. Escritórios de advocacia que imprimem todos os processos, oficiais de justiça que entregam intimações em papel, estabelecimentos que emitem nota fiscal física todos são exemplos de que a digitalização plena ainda não é universal.

No Brasil, com mais de 20 milhões de CNPJs ativos, a distribuição entre as ondas é extremamente desigual. Burocracia, cultura organizacional e infraestrutura limitada em algumas regiões tornam essa transição mais lenta do que a narrativa do mercado de tecnologia sugere. Reconhecer isso é essencial para calibrar expectativas ao avaliar um cliente ou projeto.


## Onda 2 Cloud, Mobile e Microsserviços (~2015 a 2022)

A segunda onda trouxe a migração para a nuvem, a adoção de arquiteturas mobile-first, microsserviços, observabilidade e escalabilidade. Grande parte das disciplinas de pós-graduação em tecnologia opera nessa onda e é aqui que a maioria dos profissionais de infraestrutura e desenvolvimento construiu sua experiência nos últimos anos.

O problema é que muitas empresas **dizem** que estão na onda dois sem de fato estarem. Subir um servidor para a nuvem e parar por aí não é cloud é o chamado "lift and shift", um copia e cola que apenas muda onde o problema reside, sem aproveitar os benefícios reais de uma arquitetura cloud-native. Uma empresa verdadeiramente na onda dois pensa em APIs, em microsserviços independentes, em escalabilidade, em observabilidade e consegue responder com clareza sobre como esses recursos funcionam dentro da sua operação.


## Onda 3 IA, Agentes e Automação Inteligente (2022 em diante)

A terceira onda é onde estamos: o ciclo de hype dos agentes autônomos, modelos de linguagem, automação de fluxos e IA generativa aplicada a processos de negócio. Agentes autônomos executam fluxos complexos com múltiplas chamadas de ferramentas, memória persistente e capacidade de replanejamento mas isso traz uma responsabilidade que muitas implementações ignoram: os **guardrails**.

Um caso real ilustra o risco: uma IA de uma empresa de destaque apagou o banco de dados de um cliente porque os operadores simplesmente a deixaram rodar de forma autônoma, sem regras obrigatórias que limitassem suas ações. Guardrails não são opcionais são a primeira coisa a ser definida antes de qualquer implementação. Na prática, profissionais experientes passam mais tempo construindo as regras do que o agente **não pode** fazer do que efetivamente desenvolvendo a solução. Esse investimento inicial em restrições e limites é o que garante produtividade e segurança no longo prazo.

A regra fundamental permanece: **toda entrega de IA deve ser revisada por um ser humano**, sem exceção, até que o nível de qualidade da entrega seja consistente o suficiente para que a revisão se torne cada vez mais uma validação do que uma correção. A confiança se constrói com tempo e evidência, não com fé cega na ferramenta.



---


# Tokens

Uma ilusão comum é que os modelos de linguagem "leem" texto como um humano lê. Na realidade, os LLMs não processam texto eles processam **vetores numéricos**. O texto que você digita passa por duas transformações antes de chegar ao modelo: tokenização e embedding.

Um **token** é um fragmento de texto transformado em um número inteiro. O algoritmo de tokenização (BPE Byte Pair Encoding) começa com letras individuais e vai unindo pares frequentes até montar um vocabulário de 50 a 200 mil tokens. O resultado é:

- Palavras comuns viram **um único token** (ex: "inteligência" → 1 token)
- Palavras raras ou longas viram **vários tokens** (ex: uma palavra técnica incomum → 3-4 tokens)
- Palavras inventadas consomem **muitos tokens** porque nenhum mapeamento existe para elas

### Implicações práticas dos tokens

**1. PDFs e documentos longos:** Um PDF de 200 páginas requer uma janela de contexto enorme. Modelos antigos como GPT-4 tinham janelas de 128 mil tokens insuficiente para documentos muito longos. Modelos modernos como GPT-4.5 e Claude chegam a **1 milhão de tokens** de janela de contexto, permitindo processar documentos completos.

**2. Respostas longas custam mais:** No modelo de cobrança por token, respostas longas custam em média **3 vezes mais** do que prompts longos. Se você envia um prompt complexo, peça respostas diretas e concisas isso reduz custo sem comprometer a qualidade.

**3. Código consome muitos tokens:** Código tem muitos espaços em branco, símbolos e estruturas que todos geram tokens. Ao desenvolver com IA, trabalhe em **pedaços pequenos** resolva um problema de cada vez em vez de tentar resolver tudo em uma única sessão.

**4. Português custa mais que inglês:** O vocabulário de tokenização foi treinado predominantemente em inglês. O mesmo texto em português consume aproximadamente **30% mais tokens** do que em inglês, porque palavras e construções portuguesas são menos representadas no vocabulário do tokenizador. Para tarefas de alto volume ou custo crítico, considerar prompts em inglês pode gerar economia significativa.

**5. O "esquecimento" do contexto:** Quando a janela de contexto se esgota, o modelo começa a "esquecer" informações antigas para processar as novas. Isso explica por que assistentes de código como o GitHub Copilot "esquecem" funções criadas há pouco tempo elas saíram da janela de contexto ativa.

Após a tokenização, cada token é transformado em um **embedding** uma lista de números reais de alta dimensão. Nos modelos modernos da OpenAI, cada token é representado por um vetor de **3.072 dimensões**.

### A propriedade fundamental dos embeddings

**Vetores próximos no espaço representam conceitos semanticamente próximos.** Isso significa:

- O vetor de "rei" fica próximo do vetor de "rainha"
- O vetor de "homem" fica próximo do vetor de "mulher"
- O vetor de "rei" fica distante do vetor de "banana"

A relação matemática clássica que demonstra isso: `rei - homem + mulher ≈ rainha`. Os embeddings capturam relações semânticas em álgebra linear uma descoberta revolucionária documentada em 2012 que todos os LLMs modernos herdaram e levaram a um nível muito mais sofisticado.

### Similaridade de Cosseno

A métrica usada para medir a proximidade entre vetores é a **similaridade de cosseno** o cosseno do ângulo entre dois vetores. Quanto mais próximo de 1 (ângulo de 0°), mais similares os vetores; quanto mais próximo de 0 (ângulo de 90°), mais diferentes.

Isso é poderoso porque **funciona mesmo quando a pergunta e o documento não compartilham as mesmas palavras** a similaridade é calculada sobre significado, não sobre forma. Uma busca por "encerramento de contrato" pode encontrar documentos que usam "rescisão de acordo" ou "término de vínculo" porque no espaço vetorial, esses conceitos ficam próximos.

### Por que isso importa para o RAG

O padrão **RAG (Retrieval Augmented Generation)** depende diretamente desses dois conceitos. Quando você tem uma base de documentos e quer que um modelo responda perguntas sobre eles:

1. Os documentos são transformados em tokens e depois em embeddings vetores que representam seu significado
2. A pergunta do usuário também é transformada em um vetor no mesmo espaço
3. O sistema busca os trechos dos documentos com **maior similaridade de cosseno** em relação ao vetor da pergunta
4. Os trechos mais relevantes são enviados ao LLM como contexto para gerar a resposta




---

# Prompt

<img width="1536" height="1024" alt="ChatGPT Image 4 de jun  de 2026, 16_42_10" src="https://github.com/user-attachments/assets/6ab0d6b6-4987-4110-a72c-82f7ab4c7065" />


Os prompts são essas telinhas pretas onde passamos comandos, provavelmente você já deve ter visto, mas quando começaram a surgir ferramentas de Inteligência Artificial, criou-se muita complexidade em relação a prompts e diversas maneiras de extrair qualidade das respostas obtidas. Para lidar com isso, surgiu uma nova profissão: o engenheiro de prompts.

Basicamente, o prompt é o comando ou a instrução que uma pessoa fornece a um sistema de inteligência artificial para extrair o máximo de resultado possível. Em ferramentas como o ChatGPT, o prompt é o texto digitado na área de conversa, solicitando algo da ferramenta. Assim, o prompt representa a forma como interagimos com o modelo de IA é por meio dele que dizemos o que queremos, como queremos e em que formato esperamos a resposta.

O paradigma mais simples: você faz uma pergunta e o modelo responde com base no que aprendeu durante o treinamento. É o comportamento padrão de um chat convencional tradução, classificação, geração de texto, resumos. Funciona bem para tarefas mais genéricas, mas carrega limitações estruturais importantes, como o corte de data do treinamento e a ausência de acesso a dados privados ou atualizados. Antigamente, quando os modelos ainda estavam em ascensão de aprendizado, essas limitações eram sentidas com muito mais intensidade no dia a dia.

Podemos imaginar a inteligência artificial como um supercomputador com vasto conhecimento. O papel do engenheiro de prompt é escrever instruções claras, detalhadas e bem estruturadas, capazes de filtrar esse conhecimento imenso e retornar apenas as informações mais relevantes e precisas. O objetivo é evitar respostas genéricas ou aleatórias, buscando resultados contextualizados, direcionados e assertivos. O engenheiro de prompt reduz a aleatoriedade das respostas, estabelecendo moldes, regras e padrões que a IA deve seguir.

Resumidamente, o Prompt Engineering é a arte e a ciência de criar mensagens claras e eficazes para computadores, explorando ao máximo o potencial de ferramentas como ChatGPT, Midjourney ou outras IAs. Grande parte dessas ferramentas opera por meio de comandos textuais, e compreender o conceito de engenharia de prompt é essencial para obter bons resultados. O engenheiro de prompt atua criando instruções que orientam a IA a responder conforme o objetivo, adicionando regras, definindo o tom da conversa e estruturando padrões.

Hoje, essa habilidade se tornou tão valiosa que já existe um mercado voltado exclusivamente para ela. Muitas pessoas vendem prompts prontos, otimizados para finalidades específicas — o que demonstra o poder e o valor desse conhecimento. Engana-se quem pensa que um prompt é apenas uma pergunta simples. Ele é, na verdade, um mecanismo poderoso de comunicação e controle, que define a qualidade da interação com o modelo de inteligência artificial.


---

# Engenheiros de Prompt

<img width="1536" height="1024" alt="ChatGPT Image 4 de jun  de 2026, 16_45_41" src="https://github.com/user-attachments/assets/60d7f51e-a2a4-455d-a562-a39969ff384a" />

São pessoas especializadas em passar as instruções de forma adequada para gerar as melhores respostas pelas IAs, basicamente a pessoa que foca em extrair o máximo de um prompt através de algum terminal, como o ChatGPT, onde você escreve para conversar com a ferramenta. O papel desse profissional é escrever prompts otimizados para filtrar o vasto conhecimento da Inteligência Artificial e retornar respostas mais esperadas, contextualizadas e com resultados dentro de algum molde ou premissa, reduzindo a aleatoriedade e trazendo respostas mais assertivas. Em resumo, o prompt engineering é a arte ou ciência de criar mensagens claras para computadores, extraindo o maior potencial de ferramentas de IA que funcionam por comandos.

Todo o conceito de prompt engineering envolve filtrar informações, adicionar regras, criar padrões de conversa e estruturar mensagens para que a IA entregue respostas úteis e relevantes. Não é apenas fazer uma pergunta ou pedido; é construir prompts estruturados que obtenham resultados profissionais. Por isso, é uma profissão em crescimento, e prompts bem elaborados podem gerar resultados poderosos, muito além do simples uso de ferramentas como ChatGPT.

Para escrever prompts mais profissionais, existem algumas regras importantes. A primeira é ser específico. Quanto mais específico você for, melhor será a resposta da IA, pois ela concentrará seu conhecimento na área desejada. Por exemplo, em vez de pedir algo amplo como “fale sobre engenharia civil”, um prompt forte seria: “Descreva os desafios enfrentados na construção de pontes suspensas e forneça exemplos de soluções inovadoras”. Esse nível de especificidade direciona a IA a entregar uma resposta mais focada e útil.

Outra prática importante é fornecer contexto adequado. Muitas pessoas pedem respostas sem contextualizar, o que gera respostas genéricas. Por exemplo, em vez de solicitar “Projete um sistema de abastecimento de água”, um prompt mais forte seria: “Você foi contratado para projetar um sistema de abastecimento de água em uma área rural, considerando limitações orçamentárias e ambientais”. Com isso, a resposta será delimitada, relevante e adequada à situação apresentada.

Também é recomendado estimular a aplicação prática do conhecimento. Pedir respostas que indiquem como aplicar um conceito em um cenário real aumenta a utilidade da resposta. Por exemplo, em vez de apenas explicar as leis da termodinâmica, um prompt forte seria: “Você está projetando um sistema de refrigeração para um data center. Explique as leis da termodinâmica relevantes para este projeto e como aplicá-las para maximizar a eficiência energética”. Esse tipo de prompt combina contexto e aplicação prática.

Por fim, é essencial estimular uma comunicação clara e natural. Trate a IA como trataria um ser humano, utilizando linguagem compreensível e organizada. Em vez de pedir de forma seca e técnica, explique claramente o que deseja, forneça exemplos, contexto e aplicação prática. Por exemplo, em vez de “Resolva a equação diferencial”, um prompt forte seria: “Explique passo a passo como resolver uma equação diferencial de primeira ordem usando o método de separação de variáveis e ilustre com um exemplo numérico”.

Seguindo essas práticas, você consegue extrair o máximo de uma ferramenta de IA, obtendo respostas mais claras, assertivas e contextualizadas. Sempre valide o conhecimento gerado, mas utilize essas ferramentas como aceleradoras do seu aprendizado ou como suporte para conhecimento complexo, comunicando-se de forma clara e estruturada. Isso aumentará significativamente a qualidade dos resultados obtidos.


---


# RAG

<img width="1536" height="1024" alt="ChatGPT Image 4 de jun  de 2026, 16_48_52" src="https://github.com/user-attachments/assets/b77f7fc2-bb09-448d-8b2f-20a8abea60c1" />

RAG Retrieval-Augmented Generation

O paradigma onde está a grande maioria das aplicações corporativas hoje no Brasil e no mundo. No RAG, você mantém seus dados em um armazenamento vetorial (Vector Store) e, para cada pergunta recebida, recupera os trechos mais relevantes desse repositório antes de gerar a resposta. O modelo não precisa ter aprendido aquele conteúdo no treinamento ele consulta a base de conhecimento em tempo real.

Esse paradigma resolve dois problemas centrais: o acesso a **dados privados** da organização e a **atualização contínua** do conhecimento disponível. Estima-se que aproximadamente 90% dos projetos práticos de IA em produção sejam baseados no paradigma RAG, justamente por sua capacidade de trabalhar com domínios específicos sem exigir retreinamento do modelo base.

**O RAG resolve 90% dos casos com 10% do custo do fine-tuning.** Para a grande maioria dos projetos corporativos, o paradigma RAG já é suficiente para entregar valor real. O fine-tuning deve ser considerado quando há uma necessidade genuína de especialização de domínio que o RAG por si só não resolve.

1. Ingestão de Documentos
O primeiro passo é armazenar os documentos brutos em um local acessível. O Azure Blob Storage é o serviço padrão para isso. Para automação do carregamento, o Azure Data Factory pode orquestrar pipelines de ingestão por exemplo, prontuários médicos ou peças jurídicas sendo automaticamente carregadas no Blob Storage à medida que são gerados.

2. Extração de Conteúdo
Os documentos brutos (PDFs, imagens, formulários) precisam ter seu conteúdo extraído de forma estruturada. O Azure Document Intelligence é o serviço indicado para essa etapa extraindo texto, tabelas e estruturas visuais de forma organizada, preservando o layout e o significado do conteúdo.

3. Chunking (Fragmentação)
Os documentos extraídos são divididos em pedaços menores os chunks para que possam ser indexados e recuperados com precisão. Cada chunk precisa ser semanticamente coerente: um pedaço de texto que faça sentido sozinho, sem perder o contexto do que está tratando.

4. Embedding (Vetorização)
Cada chunk é passado por um modelo de embedding como o text-embedding-3-large da OpenAI que transforma o texto em um vetor numérico de alta dimensão. Esses vetores representam matematicamente o significado do conteúdo, permitindo busca por similaridade semântica.

5. Indexação no Banco Vetorial
Os vetores gerados são armazenados no Azure AI Search (antigo Cognitive Search, agora parte do Foundry como Foundry AI Knowledge). O banco vetorial armazena os vetores junto com metadados como nome do arquivo, número da página, data que serão usados para rastreabilidade e citação de fontes.

6. Recuperação e Geração
Quando o usuário faz uma pergunta:

O prompt é vetorizado com o mesmo modelo de embedding utilizado na indexação
O sistema busca no banco vetorial os chunks com maior similaridade semântica ao prompt
Os chunks recuperados são injetados no contexto do LLM junto com o prompt original
O LLM gera uma resposta fundamentada nos documentos recuperados, podendo citar as fontes automaticamente


---

# Agente (Agent Single-Shot)

O agente representa um salto qualitativo. Trata-se de um LLM autônomo que recebe um objetivo, decide quais ações tomar, chama as ferramentas necessárias e retorna um resultado. O termo *single-shot* indica que ele opera dentro de uma decisão de alto nível: possivelmente realiza várias chamadas de ferramentas, mas não entra em um loop indefinido.

O agente é **finito** ele executa até completar uma tarefa determinada e encerra a entrega. Exemplos práticos incluem os assistentes de ferramentas como o OpenAI Assistant e agentes configurados em plataformas como Azure AI Foundry ou Anthropic. Eles fazem chamadas de ferramentas encadeadas, mas operam dentro de um escopo definido e sem supervisão contínua de replanejamento.


## Como o Modelo Escolhe o Token: Temperatura e Top-P

Se o modelo sempre escolhesse o token mais provável, as respostas se tornariam repetitivas e robotizadas. Para controlar esse comportamento, existem parâmetros que moldam o processo de seleção.

O principal deles é a **temperatura**. Em termos simples, temperatura baixa torna o modelo mais determinístico ele favorece as opções mais prováveis. Temperatura alta espalha as probabilidades, gerando mais variedade, mais criatividade, mas também maior risco de erro. Temperatura zero representa o máximo de determinismo: o modelo sempre escolhe o token mais provável, comportamento ideal para geração de código, por exemplo.

Outro parâmetro relevante é o **Top-P** (ou nucleus sampling). Em vez de considerar todos os tokens possíveis, o modelo considera apenas o conjunto mínimo de tokens cuja probabilidade acumulada soma 95%. O efeito prático é elegante: quando o modelo está seguro sobre a resposta, considera poucos tokens; quando está em dúvida, considera mais.

> **Nota prática:** A combinação de temperatura baixa com Top-P de 95% é uma configuração amplamente usada em produção para tarefas que exigem precisão. Temperatura zero é recomendada para código. Aumentar a temperatura pode trazer respostas mais criativas, mas eleva o risco de imprecisão e instabilidade nas entregas.




---


 # Transformer

 ## Contexto Histórico: O Que Mudou em 2017

Em 2017, oito pesquisadores do Google publicaram um paper intitulado *"Attention Is All You Need"*. Esse trabalho aposentou a tecnologia que dominava o processamento de linguagem natural há mais de 30 anos e estabeleceu a base arquitetural sobre a qual tudo que utilizamos hoje em modelos de linguagem foi construído. Antes de 2017, não existia uma arquitetura capaz de levar ao desenvolvimento de LLMs como o GPT ou modelos da Anthropic nada do que conhecemos hoje seria possível sem essa ruptura.

O time do Google identificou um novo paradigma de arquitetura para linguagem natural que permitiu compreender como funcionam e como escalar modelos de Inteligência Artificial de forma exponencial.

 

## O Problema das Arquiteturas Anteriores

Para entender a relevância do Transformer, é preciso compreender o problema que ele veio resolver. As arquiteturas anteriores processavam texto de forma **sequencial** palavra por palavra, como uma leitura em fita. Para chegar à décima palavra de uma frase, o modelo precisava, obrigatoriamente, passar por todas as anteriores.

Essa abordagem gerava dois problemas graves:

**1. Lentidão no treinamento.** O modelo não conseguia processar os dados em paralelo. Cada token dependia do anterior para ser computado, tornando o treinamento de textos longos extremamente ineficiente.

**2. Perda de contexto (esquecimento).** A cada nova palavra processada, as informações mais antigas tendiam a se perder. Em sequências longas com mais de 200 palavras, por exemplo o modelo frequentemente perdia o fio condutor do que havia sido processado mais cedo. Isso tornava a manutenção de contexto em conversas ou documentos extensos um problema estrutural praticamente insolúvel naquelas arquiteturas.

 

## A Proposta do Transformer

O Transformer rompeu completamente com essa lógica sequencial. Em vez de processar uma palavra de cada vez, ele **olha para a frase inteira de uma só vez**, calculando para cada palavra quais outras palavras dentro da frase são relevantes para seu entendimento.

Um exemplo ilustrativo: na frase *"O gerente disse que ele vai aprovar o relatório"*, para entender a quem o pronome "ele" se refere, um leitor humano olha automaticamente para o substantivo "gerente". O Transformer faz exatamente isso de forma matemática e simultânea para todos os pares de palavras da frase ao mesmo tempo.

Ao invés de uma leitura linear, o modelo constrói uma representação contextualizada de cada token levando em conta o contexto global da frase desde o início do processamento.



## Self-Attention: O Mecanismo Central

Junto com a arquitetura Transformer, o paper introduziu o conceito de **Self-Attention** (atenção própria). O mecanismo funciona da seguinte forma:

Para cada palavra (ou token) de uma frase, o modelo calcula um **score de relevância** em relação a todos os outros tokens da mesma frase. Esses scores são normalizados e usados para produzir uma representação ponderada ou seja, cada palavra recebe uma saída que já incorpora o contexto de toda a frase ao seu redor.

> **Nota:** Existe uma fórmula matemática associada ao Self-Attention apresentada nos slides da disciplina. Não é necessário memorizá-la neste momento; o importante é compreender o princípio: o modelo calcula pesos de relevância entre tokens, normaliza esses pesos e os usa para combinar o conteúdo de forma contextualizada.

O resultado é que, ao final desse processo, cada token carrega uma representação que **já incorpora o significado do texto completo** e todo esse processamento ocorre em paralelo.

 

## Por Que Isso Importa: Escala e Comportamentos Emergentes

O fato de o Transformer processar toda a frase em paralelo foi o que viabilizou o treinamento em larga escala. Combinado com a capacidade de representar tokens como vetores numéricos, o modelo consegue lidar com volumes massivos de dados de treino de forma eficiente.

O efeito acumulado disso é o que explica os **oito anos de evolução acelerada** observados de 2017 até hoje: quanto mais parâmetros, quanto mais dados de treinamento e quanto mais capacidade computacional, mais os modelos melhoram. E, nesse processo de escala, começam a surgir **comportamentos que ninguém programou explicitamente** capacidades emergentes que os próprios desenvolvedores não anteciparam.

Um exemplo recente e notável são modelos que, sem instrução direta, identificaram e corrigiram vulnerabilidades críticas de segurança: bugs com mais de 26 anos de existência que nenhum time humano havia detectado, além de centenas de falhas em ferramentas amplamente utilizadas como o Firefox. Esses comportamentos emergentes representam uma das fronteiras mais relevantes e desafiadoras da IA atual.

 

## As Três Variantes de Arquitetura Transformer

No contexto dos serviços de IA encontrados na prática, existem três variantes principais derivadas da arquitetura Transformer:

| Variante | Direção de Leitura | Uso Principal | Exemplos |
|---|---|---|---|
| **Encoder-Only** | Bidirecional (lê nos dois sentidos) | Compreensão e geração de embeddings | BERT |
| **Decoder-Only** | Unidirecional (lê apenas o que veio antes e gera o próximo token) | Geração de texto (modelos generativos) | GPT, Claude, Gemini |
| **Encoder-Decoder** | Combina os dois | Tradução, sumarização | Google Translate |

Os modelos generativos que usamos no dia a dia como o ChatGPT, o Claude e similares são baseados na arquitetura **Decoder-Only**: recebem um input e geram uma resposta token a token, sempre condicionada ao que veio antes. A variante **Encoder-Decoder** é empregada em tarefas que exigem tanto compreensão profunda do texto de entrada quanto geração estruturada de saída, como tradução automática.

Compreender qual variante está por trás de cada serviço é fundamental para entender o comportamento e as limitações de cada modelo tema que será retomado nas próximas aulas e laboratórios da disciplina.

 



 

É assim que o RAG permite que um modelo responda perguntas sobre documentos que nunca viu durante o treinamento e por isso a qualidade dos embeddings e a estratégia de chunking impactam diretamente a qualidade das respostas.



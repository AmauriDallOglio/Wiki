# As Etapas do Pipeline de RAG

<img width="1024" height="1536" alt="Copilot_20260603_222251" src="https://github.com/user-attachments/assets/f4c311f8-c82e-437b-9aa7-77c41878bb16" />


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

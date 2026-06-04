# Prompt

<img width="1536" height="1024" alt="ChatGPT Image 4 de jun  de 2026, 16_42_10" src="https://github.com/user-attachments/assets/6ab0d6b6-4987-4110-a72c-82f7ab4c7065" />


Os prompts são essas telinhas pretas onde passamos comandos, provavelmente você já deve ter visto, mas quando começaram a surgir ferramentas de Inteligência Artificial, criou-se muita complexidade em relação a prompts e diversas maneiras de extrair qualidade das respostas obtidas. Para lidar com isso, surgiu uma nova profissão: o engenheiro de prompts.

Basicamente, o prompt é o comando ou a instrução que uma pessoa fornece a um sistema de inteligência artificial para extrair o máximo de resultado possível. Em ferramentas como o ChatGPT, o prompt é o texto digitado na área de conversa, solicitando algo da ferramenta. Assim, o prompt representa a forma como interagimos com o modelo de IA é por meio dele que dizemos o que queremos, como queremos e em que formato esperamos a resposta.

Podemos imaginar a inteligência artificial como um supercomputador com vasto conhecimento. O papel do engenheiro de prompt é escrever instruções claras, detalhadas e bem estruturadas, capazes de filtrar esse conhecimento imenso e retornar apenas as informações mais relevantes e precisas. O objetivo é evitar respostas genéricas ou aleatórias, buscando resultados contextualizados, direcionados e assertivos. O engenheiro de prompt reduz a aleatoriedade das respostas, estabelecendo moldes, regras e padrões que a IA deve seguir.

Resumidamente, o Prompt Engineering é a arte e a ciência de criar mensagens claras e eficazes para computadores, explorando ao máximo o potencial de ferramentas como ChatGPT, Midjourney ou outras IAs. Grande parte dessas ferramentas opera por meio de comandos textuais, e compreender o conceito de engenharia de prompt é essencial para obter bons resultados. O engenheiro de prompt atua criando instruções que orientam a IA a responder conforme o objetivo, adicionando regras, definindo o tom da conversa e estruturando padrões.

Hoje, essa habilidade se tornou tão valiosa que já existe um mercado voltado exclusivamente para ela. Muitas pessoas vendem prompts prontos, otimizados para finalidades específicas — o que demonstra o poder e o valor desse conhecimento. Engana-se quem pensa que um prompt é apenas uma pergunta simples. Ele é, na verdade, um mecanismo poderoso de comunicação e controle, que define a qualidade da interação com o modelo de inteligência artificial.

# Engenheiros de Prompt

<img width="1536" height="1024" alt="ChatGPT Image 4 de jun  de 2026, 16_45_41" src="https://github.com/user-attachments/assets/60d7f51e-a2a4-455d-a562-a39969ff384a" />

São pessoas especializadas em passar as instruções de forma adequada para gerar as melhores respostas pelas IAs, basicamente a pessoa que foca em extrair o máximo de um prompt através de algum terminal, como o ChatGPT, onde você escreve para conversar com a ferramenta. O papel desse profissional é escrever prompts otimizados para filtrar o vasto conhecimento da Inteligência Artificial e retornar respostas mais esperadas, contextualizadas e com resultados dentro de algum molde ou premissa, reduzindo a aleatoriedade e trazendo respostas mais assertivas. Em resumo, o prompt engineering é a arte ou ciência de criar mensagens claras para computadores, extraindo o maior potencial de ferramentas de IA que funcionam por comandos.

Todo o conceito de prompt engineering envolve filtrar informações, adicionar regras, criar padrões de conversa e estruturar mensagens para que a IA entregue respostas úteis e relevantes. Não é apenas fazer uma pergunta ou pedido; é construir prompts estruturados que obtenham resultados profissionais. Por isso, é uma profissão em crescimento, e prompts bem elaborados podem gerar resultados poderosos, muito além do simples uso de ferramentas como ChatGPT.

Para escrever prompts mais profissionais, existem algumas regras importantes. A primeira é ser específico. Quanto mais específico você for, melhor será a resposta da IA, pois ela concentrará seu conhecimento na área desejada. Por exemplo, em vez de pedir algo amplo como “fale sobre engenharia civil”, um prompt forte seria: “Descreva os desafios enfrentados na construção de pontes suspensas e forneça exemplos de soluções inovadoras”. Esse nível de especificidade direciona a IA a entregar uma resposta mais focada e útil.

Outra prática importante é fornecer contexto adequado. Muitas pessoas pedem respostas sem contextualizar, o que gera respostas genéricas. Por exemplo, em vez de solicitar “Projete um sistema de abastecimento de água”, um prompt mais forte seria: “Você foi contratado para projetar um sistema de abastecimento de água em uma área rural, considerando limitações orçamentárias e ambientais”. Com isso, a resposta será delimitada, relevante e adequada à situação apresentada.

Também é recomendado estimular a aplicação prática do conhecimento. Pedir respostas que indiquem como aplicar um conceito em um cenário real aumenta a utilidade da resposta. Por exemplo, em vez de apenas explicar as leis da termodinâmica, um prompt forte seria: “Você está projetando um sistema de refrigeração para um data center. Explique as leis da termodinâmica relevantes para este projeto e como aplicá-las para maximizar a eficiência energética”. Esse tipo de prompt combina contexto e aplicação prática.

Por fim, é essencial estimular uma comunicação clara e natural. Trate a IA como trataria um ser humano, utilizando linguagem compreensível e organizada. Em vez de pedir de forma seca e técnica, explique claramente o que deseja, forneça exemplos, contexto e aplicação prática. Por exemplo, em vez de “Resolva a equação diferencial”, um prompt forte seria: “Explique passo a passo como resolver uma equação diferencial de primeira ordem usando o método de separação de variáveis e ilustre com um exemplo numérico”.

Seguindo essas práticas, você consegue extrair o máximo de uma ferramenta de IA, obtendo respostas mais claras, assertivas e contextualizadas. Sempre valide o conhecimento gerado, mas utilize essas ferramentas como aceleradoras do seu aprendizado ou como suporte para conhecimento complexo, comunicando-se de forma clara e estruturada. Isso aumentará significativamente a qualidade dos resultados obtidos.


# As Etapas do Pipeline de RAG

<img width="1536" height="1024" alt="ChatGPT Image 4 de jun  de 2026, 16_48_52" src="https://github.com/user-attachments/assets/b77f7fc2-bb09-448d-8b2f-20a8abea60c1" />


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

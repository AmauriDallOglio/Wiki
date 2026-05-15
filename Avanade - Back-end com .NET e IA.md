


Avanade - Back-end com .NET e IA

<img width="125" height="120" alt="image" src="https://github.com/user-attachments/assets/ef6b908f-9873-42a3-8368-424c4f18c505" />


- Introdução a Serviços de IA na Cloud com a Azure


# Conhecendo o Language Studio

Análise de Sentimentos com Language Studio no Azure AI

Continuando nosso estudo, vamos realizar agora um laboratório sobre o Language Studio. Antes disso, vale recapitular suas principais funcionalidades. O Language Studio nos auxilia na análise semântica de textos e falas, utilizando estratégias de análise de sentimentos. Como ele realiza o processamento de linguagem natural (PLN), um dos ramos da Inteligência Artificial, conseguimos interpretar mensagens, textos e diferentes formas de linguagem de maneira automatizada.

Imagine, por exemplo, uma rede de hotéis que disponibiliza seus serviços para clientes durante férias, passeios ou viagens de negócios. Após a estadia, os hóspedes podem deixar comentários avaliando sua experiência, destacando pontos positivos e negativos. Com base nesses comentários, a empresa consegue identificar quais unidades possuem melhor avaliação e quais apresentam maior número de reclamações.

Quando existe apenas um hotel, seria possível realizar essa análise manualmente, lendo cada comentário individualmente. Porém, em uma rede grande, essa tarefa se torna inviável devido ao enorme volume de informações. É nesse cenário que a análise de texto se torna fundamental, permitindo interpretar automaticamente os comentários e identificar problemas, tendências e oportunidades de melhoria.

O primeiro passo para realizar esse processo é criar um recurso de idioma dentro do portal do Azure. Após a criação desse recurso, ele será associado ao Language Studio para que possamos utilizar os serviços de análise de sentimentos.

<img width="927" height="341" alt="image" src="https://github.com/user-attachments/assets/9d5d571c-f786-47fd-a8e8-f1e14991712a" />


O caminho utilizado é o tradicional dentro do portal Azure: criar um recurso de Inteligência Artificial e Machine Learning. Nesse caso, utilizaremos o serviço de idioma, também chamado de serviço de linguagem. Ao acessar essa opção pela primeira vez, será necessário criar o recurso correspondente.

Durante a configuração, selecionamos o grupo de recursos, definimos um nome para o serviço e escolhemos o plano F0, que disponibiliza 30 dias gratuitos para avaliação. Também realizamos a validação dos campos obrigatórios. Vale lembrar que o botão de validação apenas verifica permissões, créditos disponíveis e demais requisitos necessários para criação do recurso, sem efetivamente criar nada naquele momento.

<img width="828" height="570" alt="image" src="https://github.com/user-attachments/assets/61077f5c-8548-4132-ba9a-c59707387a23" />


Após a validação, o recurso é criado e o deploy é finalizado. Com o serviço ativo, acessamos o Language Studio para associar o recurso recém-criado ao ambiente de linguagem cognitiva.

Ao abrir o Language Studio, selecionamos a assinatura, escolhemos o tipo de serviço de linguagem e vinculamos o recurso criado anteriormente. 

<img width="992" height="636" alt="image" src="https://github.com/user-attachments/assets/8b4c56a1-ded2-476b-ab56-b516d0ebb211" />

Depois disso, o sistema apresenta uma mensagem de boas-vindas e permite criar um novo projeto.

<img width="938" height="298" alt="image" src="https://github.com/user-attachments/assets/dd7b8430-7064-432f-8da8-e392f7065bca" />

Neste laboratório, utilizaremos a funcionalidade de Classificação de Texto, especificamente a opção de Análise de Sentimentos e Opiniões. O idioma será mantido em inglês e o recurso previamente criado já aparecerá selecionado automaticamente.

<img width="943" height="509" alt="image" src="https://github.com/user-attachments/assets/693b4d2c-cfdc-44bb-bebf-b61f655607b2" />

Nesse ponto, podemos inserir manualmente um texto ou utilizar um arquivo de exemplo fornecido pela própria documentação. Após carregar o texto, iniciamos o processamento para que o sistema realize a análise.
<img width="819" height="543" alt="image" src="https://github.com/user-attachments/assets/fe3df387-7db1-4439-9a0e-e960bd0ca973" />

O resultado apresentado é extremamente interessante, pois o serviço identifica automaticamente os sentimentos expressos no texto. No exemplo analisado, o sistema classificou o comentário como altamente negativo, atribuindo aproximadamente 96% de negatividade.

<img width="874" height="495" alt="image" src="https://github.com/user-attachments/assets/10cdeb59-bf2f-42e4-9738-8d6a97d26127" />

Além da classificação geral, o serviço também identifica palavras-chave e trechos específicos responsáveis pelo resultado. O comentário analisado relatava problemas relacionados à qualidade do serviço, conservação do hotel e funcionamento da internet.

<img width="941" height="580" alt="image" src="https://github.com/user-attachments/assets/5813a6f3-401d-4623-a3e8-ca18a869df64" />

O sistema conseguiu identificar frases como:

- Serviço ruim;
- Hotel antigo;
- Móveis medianos;
- Internet funcionando de forma inadequada;
- Distância maior do que a informada na propaganda.

Cada sentença foi analisada individualmente. Mesmo dividindo o texto em diferentes partes, o sistema conseguiu compreender o contexto e atribuir níveis de sentimento específicos para cada trecho.

<img width="969" height="587" alt="image" src="https://github.com/user-attachments/assets/67f208da-4b28-4a87-94f0-228e0c7bbcfe" />

No caso desse exemplo, praticamente não houve identificação de sentimentos positivos. O resultado final ficou concentrado entre neutralidade mínima e predominância extremamente negativa.

<img width="930" height="403" alt="image" src="https://github.com/user-attachments/assets/9da12471-0a40-40ef-b07c-1c3a8844cc85" />

Outro ponto importante é que a ferramenta suporta diversos idiomas, permitindo análises em cenários multinacionais. Isso é especialmente útil para empresas globais que recebem comentários de clientes em diferentes línguas e precisam consolidar rapidamente essas informações.

<img width="835" height="514" alt="image" src="https://github.com/user-attachments/assets/2bc330a2-42ce-42a1-b59a-c30c0cf9d93f" />

Essa análise de sentimentos pode ser utilizada em diferentes contextos, como:

- Avaliação de novos produtos;
- Monitoramento de campanhas promocionais;
- Feedback sobre serviços de entrega;
- Aplicativos de transporte;
- Companhias aéreas;
- Plataformas digitais em larga escala.

Grandes empresas lidam diariamente com milhares ou até milhões de comentários. Realizar uma análise manual seria praticamente impossível. Com o uso de Inteligência Artificial e processamento de linguagem natural, torna-se viável identificar rapidamente padrões, problemas recorrentes e percepções dos clientes.

Além disso, o próprio Language Studio fornece documentação, exemplos de código, informações de cobrança e orientações sobre responsabilidade no uso dos dados compartilhados. Isso reforça a importância do tratamento adequado das informações utilizadas nas análises.

Um ponto bastante interessante é a possibilidade de realizar testes rápidos em cenários reais. Empresas podem utilizar comentários existentes em seus aplicativos, sites ou plataformas para validar o funcionamento da ferramenta e demonstrar seu valor para áreas gerenciais e estratégicas.

Ver a solução funcionando na prática ajuda a comprovar sua eficiência, independentemente do tamanho da empresa ou da escala de utilização. Além disso, desenvolver habilidades relacionadas ao uso dessas tecnologias agrega muito valor profissionalmente, principalmente em áreas ligadas à Inteligência Artificial e análise de dados.

Espero que você tenha gostado deste laboratório sobre o Language Studio e análise de sentimentos utilizando Azure AI. Agora podemos seguir para o próximo conteúdo.




# Entendendo Desafio 

Agora é a sua hora de brilhar e construir um perfil de destaque na DIO! Explore todos os conceitos abordados até aqui, aplique os conhecimentos adquiridos nas aulas e documente sua experiência para demonstrar sua compreensão dos temas discutidos.

# Descrição do Desafio
Este laboratório tem como objetivo praticar e aprofundar o uso das ferramentas Azure Speech Studio e Language Studio, focando na análise de fala e linguagem natural. O objetivo é desenvolver habilidades práticas na criação de soluções baseadas em inteligência artificial voltadas para voz e linguagem. O entregável é um repositório organizado contendo anotações e insights adquiridos durante a prática, servindo como material de apoio para estudos e futuras implementações.

# Objetivos de Aprendizagem 
Ao concluir este desafio, você será capaz de: 

- Aplicar os conceitos aprendidos em um ambiente prático;
- Documentar processos técnicos de forma clara e estruturada;
- Utilizar o GitHub como ferramenta para compartilhamento de documentação técnica. 
- Entrega do Desafio 
- Para concluir este desafio, você deverá: 

- Assistir a todas as vídeo-aulas
- Não pule nenhuma etapa! As aulas contêm informações essenciais para o sucesso do seu projeto. 

- Criar um repositório público no GitHub contendo: 
- Um arquivo README.md detalhado 
- Quaisquer arquivos adicionais que sejam relevantes para documentar sua experiência 
- Opcionalmente, capturas de tela relevantes organizadas em uma pasta /images 

Enviar o link do seu repositório e uma breve descrição clicando no botão “Entregar Projeto” 

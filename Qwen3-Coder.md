
O Qwen3-Coder para revisar e implementar pequenas alterações em um projeto .NET existente. 

Instalar: ollama pull qwen3-coder

<img width="1873" height="172" alt="image" src="https://github.com/user-attachments/assets/0371f45d-2fef-467d-bcae-3ae2682637df" />

Teste 1:

ollama run qwen3-coder

Aguarde o modelo carregar. Depois, digite esta pergunta: Explique o que é injeção de dependência em C# e mostre um exemplo usando ASP.NET Core.

<img width="1373" height="827" alt="image" src="https://github.com/user-attachments/assets/b7f87d95-536f-4a38-87cb-c9b5c2093f6d" />

Esse comando abre uma conversa com o modelo, mas não fornece automaticamente a estrutura nem o conteúdo da solução. Por isso, ele respondeu de forma genérica.

O próximo exemplo será teste com o projeto;

Teste 2

Descubra a estrutura do projeto: Get-ChildItem -Force

<img width="905" height="483" alt="image" src="https://github.com/user-attachments/assets/a1017bf4-d4b1-4d43-82e6-b059c2aaadb7" />

Para listar os arquivos e as pastas do projeto: tree /A

<img width="1096" height="831" alt="image" src="https://github.com/user-attachments/assets/40f81697-2333-45a0-91fa-d108a03c9392" />

Como fazer o teste com o seu projeto: tree /A | ollama run qwen3-coder "Analise a estrutura desta solução .NET. Identifique os projetos, explique a responsabilidade provável de cada um e diferencie projetos de camadas arquiteturais. Não invente informações que não estejam na estrutura."

<img width="1882" height="897" alt="image" src="https://github.com/user-attachments/assets/8a3ff3ee-f731-4b68-978d-05902e700f76" />



Exemplos de comandos:

Crie uma API REST em .NET com arquitetura em camadas, Entity Framework Core e SQL Server. Implemente CRUD, DTOs, validações e tratamento global de exceções.

Analise este código C# e identifique problemas de arquitetura, segurança, desempenho e tratamento de erros. Explique os problemas e apresente uma versão corrigida, mantendo o comportamento atual.

Projete uma solução em C# com .NET para implementar RAG usando embeddings, banco vetorial e um LLM local via Ollama. Descreva os componentes, o fluxo de recuperação, as interfaces e os testes necessários.

Como transformar o Qwen3-Coder em um agente de programação?

Para permitir que ele analise arquivos e execute tarefas de desenvolvimento, você pode integrá-lo a uma ferramenta de programação com agentes, como o Qwen Code ou o OpenCode. O Ollama documenta essas integrações.

Modelo: interpreta solicitações e gera código.

Agente: organiza as etapas e decide quando utilizar ferramentas.

Ferramentas: permitem ler arquivos, editar código, executar testes e consultar o terminal, conforme as permissões concedidas.

Como cada um se encaixa no seu ambiente:

1. Visual Studio: É onde você escreve código, depura aplicações, gerencia soluções, compila projetos e executa testes.

2. Ollama + Qwen3-Coder: Executa o modelo de IA localmente. Você pode fazer perguntas sobre código, solicitar implementações e receber sugestões pelo terminal ou por uma integração.

3. OpenCode ou Qwen Code: Permitem que um agente examine arquivos do projeto, proponha ou realize alterações e execute comandos autorizados. Podem funcionar ao lado do Visual Studio.

Imagine que você tem uma solução .NET com vários projetos e precisa criar um novo microsserviço.

- Somente Visual Studio: você cria os arquivos e implementa o código manualmente, usando os recursos de desenvolvimento da IDE.
  
- Visual Studio + Ollama: você consulta o Qwen3-Coder e aproveita as respostas para implementar o serviço.
  
- Visual Studio + agente de programação: você solicita que o agente analise a solução, implemente arquivos relacionados e execute testes, com as permissões necessárias.


  


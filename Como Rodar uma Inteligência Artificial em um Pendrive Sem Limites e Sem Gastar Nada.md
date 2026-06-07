
# Como Rodar uma Inteligência Artificial em um Pendrive Sem Limites e Sem Gastar Nada


## Primeira Etapa

<img width="1536" height="1024" alt="ChatGPT Image 6 de jun  de 2026, 20_45_47" src="https://github.com/user-attachments/assets/67faf2e7-88ed-45da-b980-6360a56a0fd3" />

Primeiro, conecte o seu pendrive ao computador e formate-o em exFat. Ele precisa ter, no mínimo, 16 GB de armazenamento e estar formatado no sistema de arquivos **exFAT**.

<img width="293" height="563" alt="image" src="https://github.com/user-attachments/assets/e9c671e8-9622-4e04-9508-17fe6bafdff6" />

Feito isso, Ao acessar a página do projeto no GitHub (https://github.com/mozilla-ai/llamafile), localize a área de download e clique no link da versão mais recente. Em seguida, desça até encontrar a seção **Releases**, onde estará disponível o primeiro arquivo para download. Basta clicar nele para baixar a última versão.

<img width="1473" height="320" alt="image" src="https://github.com/user-attachments/assets/285e51ac-0622-4ff2-afff-9768a73d0f34" />

Esse arquivo possui aproximadamente 1 GB, por isso é importante utilizar um pendrive com espaço suficiente. Após o download, renomeie o arquivo para **.exe** e copie-o para dentro do pendrive. Essa é a primeira etapa.

## Segunda Etapa

<img width="1536" height="1024" alt="ChatGPT Image 6 de jun  de 2026, 20_48_42" src="https://github.com/user-attachments/assets/a5198c43-de8e-4af2-8250-571c7b2843ad" />

Agora, acesse o site **Hugging Face**.  [https://huggingface.co/](https://huggingface.co/)

No menu **Models**, localizado na parte superior, procure a opção **GGUF** dentro da seção de bibliotecas. A partir daí, você terá acesso a milhares de modelos de inteligência artificial disponíveis para utilização.

Para começar, recomenda-se utilizar o modelo **pramodlohra/Qween3_4B_thinking_finetune**. Pesquise por ele na plataforma, clique em **Files and Versions** e faça o download de um arquivo no formato **GGUF**. ([https://huggingface.co/pramodlohra/Qween3_4B_thinking_finetune/tree/main](https://huggingface.co/pramodlohra/Qween3_4B_thinking_finetune/tree/main))

<img width="1869" height="700" alt="image" src="https://github.com/user-attachments/assets/2ba04554-852a-4b49-9db8-a3c3ccc2582a" />

Normalmente, esses arquivos possuem alguns gigabytes de tamanho. No exemplo apresentado, o arquivo possui aproximadamente **2,5 GB**.

<img width="1645" height="710" alt="image" src="https://github.com/user-attachments/assets/a8d54b2b-3901-4c1d-a8af-a885d913d205" />

Após concluir o download, copie também esse arquivo para o pendrive.


## Terceira Etapa

<img width="1536" height="1024" alt="ChatGPT Image 6 de jun  de 2026, 20_50_48" src="https://github.com/user-attachments/assets/956848f9-fd76-4515-b10e-a72cc21933c0" />


Com os dois arquivos já armazenados no pendrive,

```
llamafile-0.10.1.exe
qwen3-4b-thinking-2507.Q4_K_M.gguf
```

Abra o **Bloco de Notas** e escreva o código necessário para executar a aplicação.

O comando do seu arquivo install.bat ou iniciar.bat deveria ficar assim:

```
@echo off
```

```
.\llamafile-0.10.1.exe --server --model qwen3-4b-thinking-2507.Q4_K_M.gguf
```

```
pause
```

Ou, se quiser abrir automaticamente o navegador:

```
@echo off
```

```
start "" .\llamafile-0.10.1.exe --server --model qwen3-4b-thinking-2507.Q4_K_M.gguf
```

```
timeout /t 10
```

```
start http://localhost:8080
```

```
pause
```

Agora, clique em **Salvar Como** com a extensão .bat e grave esse arquivo diretamente no pendrive;

Esse arquivo será o responsável por executar todo o processo automaticamente.

Ao final, você deverá possuir três arquivos dentro do pendrive:

1. O executável do LlamaFire.
2. O modelo de inteligência artificial no formato GGUF.
3. O arquivo BAT responsável pela execução.
O resultado ficará semelhante ao exemplo:

Pendrive │

```
├── llamafile-0.10.1.exe
├── qwen3-4b-thinking-2507.Q4_K_M.gguf
└── iniciar.bat
```

```
.\llamafile.exe --server --model
.\llamafile.exe --server --model qwen3-4b-instruct.gguf
.\llamafile.exe --server --model llama-3.2-3b-instruct.gguf
```

## Executando a Inteligência Artificial

Pronto. Agora você tem uma inteligência artificial rodando diretamente do seu pendrive.

Carregando parte 1:
<img width="1302" height="740" alt="image" src="https://github.com/user-attachments/assets/ba6d2bca-7b49-44bc-bc1b-08f644200ded" />

Carregando parte 2:
<img width="1717" height="796" alt="image" src="https://github.com/user-attachments/assets/84471c58-bd30-47f7-a682-6ec38b2f1999" />

Carregando parte 3:
<img width="1750" height="973" alt="image" src="https://github.com/user-attachments/assets/02fc93b9-6825-495c-b4e3-eacd91936832" />


Sempre que conectar o pendrive ao computador, basta executar o arquivo **.bat** criado anteriormente.

Uma janela de comandos será aberta. Aguarde o carregamento completo do sistema. Ao final do processo, será exibido um link local.

Pressione **Ctrl** no teclado e clique sobre esse link para abri-lo no navegador.

A partir desse momento, você terá acesso a uma interface de inteligência artificial executando localmente, diretamente do seu próprio pendrive.

## Recursos Disponíveis

A interface oferece recursos semelhantes aos encontrados em assistentes de IA modernos:

* Conversas em formato de chat.
* Histórico de conversas salvo localmente.
* Suporte ao envio de arquivos.
* Suporte ao envio de imagens.
* Exibição do processo de raciocínio do modelo.
* Respostas detalhadas e contextualizadas.
* Contagem de tokens em tempo real.
* Execução local, sem depender da nuvem.
Tudo isso funcionando diretamente no seu computador e sem custos de utilização.

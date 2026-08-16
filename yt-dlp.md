# Download de Áudio e Transcrição com yt-dlp e Whisper

## 1. Objetivo

Esta documentação descreve as etapas necessárias para configurar e utilizar as ferramentas **yt-dlp**, **FFmpeg** e **Whisper** em uma API desenvolvida em **.NET**, permitindo realizar o download de áudio a partir de uma URL e posteriormente realizar sua transcrição.

O fluxo implementado é:

```text
URL do vídeo
     │
     ▼
   API .NET
     │
     ▼
  yt-dlp.exe
     │
     ▼
 Download do áudio
     │
     ▼
   FFmpeg
     │
     ▼
     MP3
     │
     ▼
  whisper.exe
     │
     ▼
 Transcrição
     │
     ▼
 Texto retornado pela API
```

---

# 2. yt-dlp

O **yt-dlp** é um programa gratuito e de código aberto utilizado para realizar o download de vídeos e áudios disponíveis na internet.

Ele funciona por meio de comandos executados no terminal e possui suporte para diversos sites e plataformas.

Entre os sites suportados estão, por exemplo:

* YouTube
* TikTok
* Instagram
* Twitch
* Facebook

Para o projeto, o yt-dlp será utilizado para realizar o download do áudio do vídeo informado pelo usuário.

---

# 3. Ferramentas necessárias

Como a API .NET será integrada ao processo de transcrição utilizando Whisper, são necessárias as seguintes ferramentas:

```text
yt-dlp.exe
ffmpeg.exe
whisper.exe
```

Como instalar whisper e ffmpeg: https://github.com/AmauriDallOglio/Wiki/blob/main/Whisper%20no%20Windows%20(para%20fazer%20transcri%C3%A7%C3%A3o%20de%20%C3%A1udio).md

Essas ferramentas podem ser armazenadas em uma única pasta.

Exemplo:

```text
C:\Ferramentas
```

Estrutura sugerida:

```text
C:\Ferramentas
│
├── yt-dlp.exe
├── ffmpeg.exe
└── whisper.exe
```

Também é possível utilizar subpastas:

```text
C:\Ferramentas
│
├── yt-dlp
│   └── yt-dlp.exe
│
├── ffmpeg
│   ├── ffmpeg.exe
│   └── ffprobe.exe
│
└── whisper
    └── whisper.exe
```


# 4. Instalação do yt-dlp

https://github.com/yt-dlp/yt-dlp/releases/tag/2026.07.04

<img width="1800" height="658" alt="image" src="https://github.com/user-attachments/assets/12098121-f5ad-47f4-a87a-3cea8eb4e5ed" />

Após realizar o download do `yt-dlp.exe`, coloque o executável na pasta:

```text
C:\Ferramentas
```

Exemplo:

```text
C:\Ferramentas\yt-dlp.exe
```

A existência do arquivo pode ser verificada pelo PowerShell:

```powershell
dir C:\Ferramentas
```

Resultado esperado:

```text
Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----                ...                   ...    yt-dlp.exe
```

---

# 5. Não executar o yt-dlp com duplo clique

O `yt-dlp.exe` é uma aplicação de linha de comando.

Portanto, ao executar o arquivo diretamente com duplo clique, poderá ser apresentada a mensagem:

```text
yt-dlp.exe: error: Do not double-click the executable,
instead call it from a command line.
```

Isso não significa que o programa está com problema.

O `yt-dlp` deve ser executado utilizando:

* Prompt de Comando (CMD)
* PowerShell
* Windows Terminal

---

# 6. Testando o yt-dlp

Abra o PowerShell e acesse a pasta onde o executável está instalado:

```powershell
cd C:\Ferramentas
```

Execute:

```powershell
yt-dlp.exe --version
```

Também é possível executar:

```powershell
.\yt-dlp.exe --version
```

O resultado deverá apresentar a versão instalada.

Exemplo:

```text
2026.07.04
```

Isso confirma que o `yt-dlp.exe` está funcionando corretamente.

---

# 7. Testando o download de áudio

Depois de validar a instalação, pode ser realizado um teste de download.

Comando:

```powershell
yt-dlp.exe -x --audio-format mp3 "URL_DO_VIDEO"
```

<img width="1805" height="596" alt="image" src="https://github.com/user-attachments/assets/5e9253e1-3e53-4b5c-bf46-0491c27bc735" />

Executar o serviço no servidor:

<img width="1516" height="352" alt="image" src="https://github.com/user-attachments/assets/1317f0a3-8cc9-4962-8975-c4e1a6eafb8c" />


---
 

# 8. FFmpeg

O **FFmpeg** é utilizado no processamento e conversão do áudio.

No fluxo da aplicação, ele é importante porque o `yt-dlp` pode realizar o download do áudio em um formato diferente, como WebM, e utilizar o FFmpeg para realizar a conversão para MP3.

A estrutura recomendada é:

```text
C:\Ferramentas
│
├── yt-dlp.exe
├── ffmpeg.exe
└── ffprobe.exe
```

O `ffprobe.exe` também é utilizado por algumas operações relacionadas ao processamento de mídia.

---

# 9. Whisper

O **Whisper** será utilizado para transformar o áudio em texto.

O processo será:

```text
MP3
 │
 ▼
Whisper
 │
 ▼
Texto
```

O arquivo utilizado pela aplicação será:

```text
whisper.exe
```

A API .NET poderá executar o Whisper utilizando `System.Diagnostics.Process`, da mesma forma que executa o `yt-dlp.exe`.

---

# 10. Estrutura da API .NET

A aplicação foi estruturada para separar as responsabilidades.

O `ProcessoServico` possui a responsabilidade de executar programas externos.

Ele pode ser utilizado para executar:

```text
yt-dlp.exe
ffmpeg.exe
whisper.exe
```

O `YoutubeServico` possui a responsabilidade de:

1. Receber a URL.
2. Validar a solicitação.
3. Preparar a pasta de destino.
4. Montar os parâmetros do yt-dlp.
5. Solicitar a execução do `yt-dlp.exe`.
6. Localizar o arquivo MP3 gerado.
7. Retornar as informações do arquivo.

A pasta utilizada no projeto é:

```text
C:\Mp3
```

---

 




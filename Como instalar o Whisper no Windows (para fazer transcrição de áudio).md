

# Instalar Python

- Baixe o Python em https://www.python.org/downloads/

<img width="1283" height="313" alt="image" src="https://github.com/user-attachments/assets/4594d6e6-983b-4226-b6f8-29e9a0a1ef38" />

- Baixe a versão: https://www.python.org/downloads/release/python-3140/ 

<img width="1426" height="487" alt="image" src="https://github.com/user-attachments/assets/4004379f-c3db-47a8-b1ac-236f273efc1c" />

Durante a instalação, marque “Add Python to PATH”.

<img width="1438" height="533" alt="image" src="https://github.com/user-attachments/assets/6841a007-2874-4a9e-93f4-86f736ee2e78" />


# Instalar o FFmpeg

No PowerShell, rodar o comando: winget install Gyan.FFmpeg

<img width="1898" height="625" alt="image" src="https://github.com/user-attachments/assets/ec1ba8e9-0b3c-4510-af7e-e810e5813011" />

Teste mostrou que o FFmpeg está instalado e funcionando corretamente no Windows PowerShell:

<img width="1883" height="632" alt="image" src="https://github.com/user-attachments/assets/f4c03fd3-5713-4aa1-ae7d-462fc7f0bdd8" />


# Instalar o Whisper via pip

No PowerShell, rode: pip install -U openai-whisper

O pip baixa e instala automaticamente o Whisper e todas as dependências necessárias (como PyTorch).
Atualizações basta rodar: pip install -U openai-whisper ;


<img width="1673" height="332" alt="image" src="https://github.com/user-attachments/assets/ab1680a5-f4b0-4b8c-885f-1ab2a7ce9d5a" />


# Atualização

python -m pip install --upgrade pip
pip install -U openai-whisper

<img width="1819" height="799" alt="image" src="https://github.com/user-attachments/assets/8ac916fc-b0ef-4b5d-b06e-f3df1802f30a" />


# Testando

Usar o comando: whisper C:\Amauri\Gravando.mp3 --model small --language pt

<img width="1337" height="115" alt="image" src="https://github.com/user-attachments/assets/f098060c-3a51-4fe8-a1a7-3169f44f6412" />


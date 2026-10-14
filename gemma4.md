
Ollama

Confira a versão:

ollama --version

<img width="1312" height="322" alt="image" src="https://github.com/user-attachments/assets/47f4e78b-e623-459b-8fea-5363cb775bc0" />

Atualize o Ollama: irm https://ollama.com/install.ps1 | iex

Feche o Ollama pela bandeja do Windows.

Baixe o instalador oficial: Ollama para Windows.

Execute o instalador e abra o Ollama novamente.


<img width="907" height="113" alt="image" src="https://github.com/user-attachments/assets/a0dc7eec-56f9-4632-855f-f358d2d9546c" />




Atualize o gemma4: ollama pull gemma4

<img width="1860" height="170" alt="image" src="https://github.com/user-attachments/assets/ff99160b-4740-49cc-91b6-f291c480a579" />
<img width="1532" height="409" alt="image" src="https://github.com/user-attachments/assets/35841c4e-ed0a-488e-83ac-5b295deb89b8" />

Feche e abra o terminal

<img width="1875" height="828" alt="image" src="https://github.com/user-attachments/assets/e76453e5-5fc8-4fde-9fdf-662aa7e1f5fd" />

Feche o PowerShell atual, abra uma nova janela e execute: ollama --version

Se ainda mostrar 0.40.3, confira qual executável está sendo utilizado: where.exe ollama

Teste o modelo de visão

Se a versão estiver atualizada, execute: ollama run llama3.2-vision

Se o modelo iniciar, ótimo. Caso apareça novamente unknown model architecture: 'mllama', copie o erro completo.

Feche o aplicativo pela bandeja do Windows. Depois, no PowerShell, execute: Get-Process *ollama* -ErrorAction SilentlyContinue

Se ainda houver processos do Ollama, encerre-os: Get-Process *ollama* -ErrorAction SilentlyContinue |     Stop-Process -Force

Isso interrompe temporariamente o serviço local.

Confira a versão do executável instalado: (Get-Item "$env:LOCALAPPDATA\Programs\Ollama\ollama.exe").VersionInfo |
    Format-List FileVersion, ProductVersion



Update: ollama pull gemma4:12b

<img width="1501" height="271" alt="image" src="https://github.com/user-attachments/assets/4be4f29e-319c-4b5b-9fce-0089ff7cbfb4" />


Testando no ollama:

<img width="1279" height="896" alt="image" src="https://github.com/user-attachments/assets/5b2ce128-0c02-4d1f-a09e-45871c8bac85" />


```text
 $imagem = "C:\Temp\hotwheels.jpg"

$base64 = [Convert]::ToBase64String(
    [System.IO.File]::ReadAllBytes($imagem)
)

$body = @{
    model = "gemma4:12b"
    prompt = "Describe the objects visible in this photo. What type of vehicle is shown? Mention its color and distinctive features."
    images = @($base64)
    stream = $false
} | ConvertTo-Json -Depth 5

$resposta = Invoke-RestMethod `
    -Uri "http://localhost:11434/api/generate" `
    -Method Post `
    -ContentType "application/json" `
    -Body $body

$resposta.response
 

```

<img width="1450" height="1025" alt="image" src="https://github.com/user-attachments/assets/09b9aae8-d29e-4861-8bfa-8773a7daf741" />


```text
Analise a imagem deste carrinho colecionável Hot Wheels.

Retorne os resultados em JSON válido, usando exatamente estes campos:

{
"categoria": "Carrinhos",
"fabricante": null,
"modelo": null,
"cor": null,
"escala": null,
"anoFabricacao": null,
"serie": null,
"inscricoesVisiveis": [],
"descricaoVisual": "",
"informacoesNaoIdentificadas": []
}

Regras:
- Identifique somente informações que possam ser observadas ou inferidas com justificativa.
- Não invente o modelo exato, o ano ou a série.
- Use null quando não houver evidências suficientes.
- Diferencie características visíveis de suposições.
- Retorne somente o JSON, sem explicações fora dele.

```








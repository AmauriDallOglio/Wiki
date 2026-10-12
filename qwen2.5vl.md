Qwen2.5-VL

Um dos modelos open source mais avançados para visão.

Capacidades:

OCR (leitura de texto).

Análise de gráficos.

Compreensão de documentos.

Imagens complexas.

Instalar: ollama run qwen2.5vl

<img width="1888" height="390" alt="image" src="https://github.com/user-attachments/assets/2a3cd845-340a-4dcf-9d02-6c86c623bda8" />


<img width="1592" height="577" alt="image" src="https://github.com/user-attachments/assets/73290c09-b8ec-4571-86bc-420193dc4d1f" />


```text

$imagem = "C:\Temp\hotwheels.jpg"
$base64 = [Convert]::ToBase64String(
    [System.IO.File]::ReadAllBytes($imagem)
)

$body = @{
    model = "llama3.2-vision:latest"
    prompt = "Descreva somente as características visíveis do carrinho na imagem."
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



<img width="1797" height="824" alt="image" src="https://github.com/user-attachments/assets/dbfbc7ef-76ce-4529-9191-b566314e2b1e" />



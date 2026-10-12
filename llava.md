
Instalar: ollama run llava

<img width="1852" height="98" alt="image" src="https://github.com/user-attachments/assets/682e9f14-5c1e-4bc6-8c39-96889b935102" />

<img width="1599" height="282" alt="image" src="https://github.com/user-attachments/assets/e0022e0d-6118-4247-88ce-7273e1eb60c3" />


$imagem = "C:\Temp\hotwheels.jpg"

$base64 = [Convert]::ToBase64String(
    [System.IO.File]::ReadAllBytes($imagem)
)

$body = @{
    model = "gemma4"
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


<img width="1889" height="932" alt="image" src="https://github.com/user-attachments/assets/53091678-6423-4922-8650-5ad3bed67929" />


<img width="1242" height="988" alt="image" src="https://github.com/user-attachments/assets/784ad259-1d2e-496e-8d5b-c05cb22c4f75" />

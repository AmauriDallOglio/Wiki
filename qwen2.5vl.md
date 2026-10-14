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
    model = "qwen2.5vl:latest"
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


<img width="1444" height="1018" alt="image" src="https://github.com/user-attachments/assets/8e898ac8-2d46-48b1-91b1-20faae80482b" />


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
- 


```


Instalar: ollama run llava

<img width="1852" height="98" alt="image" src="https://github.com/user-attachments/assets/682e9f14-5c1e-4bc6-8c39-96889b935102" />

<img width="1599" height="282" alt="image" src="https://github.com/user-attachments/assets/e0022e0d-6118-4247-88ce-7273e1eb60c3" />

Teste:


<img width="1895" height="877" alt="image" src="https://github.com/user-attachments/assets/2ddef872-87bf-4656-acf3-41d3c6fc9374" />



```text
 $imagem = "C:\Temp\hotwheels.jpg"

$base64 = [Convert]::ToBase64String(
    [System.IO.File]::ReadAllBytes($imagem)
)

$body = @{
    model = "llava:latest"
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





<img width="1452" height="1020" alt="image" src="https://github.com/user-attachments/assets/b744540f-18ea-44a5-a324-dd01e0ec8c17" />


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

# Deploy automático no Azure com GitHub Actions

Este projeto está configurado para realizar deploy contínuo no **Azure App Service** usando **GitHub Actions** e autenticação via **OIDC (OpenID Connect)**.  
Abaixo está o passo a passo completo para configurar do zero.

---

## Pré-requisitos
- Conta no Azure
- Um **App Service** criado para hospedar a aplicação  
- Permissão de acesso à assinatura do Azure  
- Repositório no GitHub com Actions habilitado  

---

## Configuração no Azure

### Criando o script do pipeline de forma manual 

<img width="1851" height="862" alt="image" src="https://github.com/user-attachments/assets/ce7431ab-3598-49be-b3b9-ed0ce6913b6e" />
<img width="1885" height="703" alt="image" src="https://github.com/user-attachments/assets/2b045363-de6b-4456-93ca-77497a064a4c" />

O que você está vendo no Deployment Center do Azure App Service é uma forma alternativa de configurar o CI/CD. 
Ele pode criar automaticamente um workflow do GitHub Actions para você, mas como você já montou manualmente o arquivo .github/workflows/azure-webapps.yml e 
adicionou os segredos no GitHub, não precisa configurar nada por aqui.

Ignore a configuração de CI/CD no Deployment Center, não é necessária porque usaremos o pipeline pronto no GitHub.

### 1. Criar App Registration

<img width="1096" height="167" alt="image" src="https://github.com/user-attachments/assets/fdedb127-bb83-4e13-8f3f-4db48879570d" />

- Acesse **Microsoft Entra ID → Registros de aplicativo → Novo registro**  

<img width="1254" height="547" alt="image" src="https://github.com/user-attachments/assets/f775169e-e226-4214-b3e0-1a4a14050e11" />

- Nome: `GitHubDeployAppSerilog`
  - É apenas o nome de exibição do aplicativo.
  - Pode ser algo como: GitHubDeployApp ou GitHubDeployAppDeploy.
  - Esse nome serve para identificar o app dentro do Azure AD.
- Tipo de conta: Somente este diretório
  - Isso significa que apenas usuários e serviços dentro do seu diretório (tenant) poderão usar esse app para autenticação.
  - É a opção mais comum quando você vai usar o app apenas para deploy da sua própria aplicação.
- URI de redirecionamento (opcional)
  - Pode deixar em branco agora.
- Salve.

<img width="1475" height="618" alt="image" src="https://github.com/user-attachments/assets/40011227-1e0d-4ee6-b5cf-54c9fcfa484f" />


### 2. Criar credencial federada (OIDC)

<img width="1406" height="166" alt="image" src="https://github.com/user-attachments/assets/1847ff34-9a99-4c5e-a8f1-d8293fdfc53b" />


<img width="1370" height="578" alt="image" src="https://github.com/user-attachments/assets/6c50be87-289b-4142-9393-3e2365881bbd" />
Erro Se AADSTS70025: The client 'GitHubDeployAppSerilog' has no configured federated identity credentials.

Vá no portal do Azure → abra Microsoft Entra ID → No painel que você mostrou, clique em Registros de aplicativo. → Na lista, selecione o app GitHubDeployAppSerilog.

<img width="1062" height="620" alt="image" src="https://github.com/user-attachments/assets/ad10072c-1ec5-41b1-94bb-26f201e5cdb5" />

- Vá em **App Registration → GitHubDeployAppSerilog →  “Certificados e segredos”  → Credenciais federadas → Adicionar**

<img width="1325" height="501" alt="image" src="https://github.com/user-attachments/assets/491b0178-64fd-4009-982c-8ea865bf69ca" />

<img width="913" height="681" alt="image" src="https://github.com/user-attachments/assets/ac4a2b8d-505b-4e6a-b1b1-7324d44b8382" />
<img width="898" height="290" alt="image" src="https://github.com/user-attachments/assets/c6da9981-9289-4a0a-8035-1e49fcea6323" />

- Emissor: `https://token.actions.githubusercontent.com`
- Organização: `AmauriDallOglio`
- Organization ID: 
- GitHub organization ID: 
- Repositório: Serilog
- Repository ID: 
- GitHub repository ID: 
- Tipo de entidade: `Ramificação`  (Branch)
  - Isso porque o seu workflow dispara sempre que há push no branch master.
- Com base na seleção: `master`
- Identificador de assunto: `repo:AmauriDallOglio/Serilog:ref:refs/heads/master`
- Nome: `GitHubActions-Serilog-Master`
- Descrição: `Credencial federada para deploy do Serilog via GitHub Actions`
- Público-alvo: `api://AzureADTokenExchange`
 
 


### 3. Dar permissão na assinatura

<img width="1597" height="622" alt="image" src="https://github.com/user-attachments/assets/00355e3c-9650-4b29-a9a1-c7d4347031df" />

<img width="1348" height="189" alt="image" src="https://github.com/user-attachments/assets/676f9bca-409c-4f88-bf6d-0b9c7a57cbbd" />

- Vá em **Assinaturas → Amauri → IAM (Controle de acesso)**  → Clique em **Adicionar atribuição de função**

<img width="1454" height="255" alt="image" src="https://github.com/user-attachments/assets/e690a68e-0158-4163-a2f6-bc414377e81d" />


- Selecione **Contribuidor** (Contribuidor geral)  

<img width="1523" height="817" alt="image" src="https://github.com/user-attachments/assets/a3ae1a65-82d3-44ab-bc54-a3395d90ef83" />

- Em **Membros**, escolha o App Registration `GitHubDeployAppSerilog`

- Salve.

<img width="1759" height="597" alt="image" src="https://github.com/user-attachments/assets/07b9e577-6858-4e5c-a9e2-1170df933eca" />

- Agora o App Registration aparece listado como **Contribuidor** na assinatura.

---

## 🔑 Secrets no GitHub

No repositório, vá em **Settings → Secrets and variables → Actions** e adicione:

- `AZURE_CLIENT_ID` → **Application (client) ID** do App Registration
  - <img width="1488" height="598" alt="image" src="https://github.com/user-attachments/assets/97a3eb9d-8fee-4512-91b4-eabdc1b665ae" />

- `AZURE_TENANT_ID` → **Tenant ID** do diretório
  - <img width="1156" height="305" alt="image" src="https://github.com/user-attachments/assets/2be619e8-a50c-4aaa-986a-bf944f37ac36" />
  - Ou em Microsoft Entra ID → Visão geral do diretório  
  - <img width="1441" height="483" alt="image" src="https://github.com/user-attachments/assets/7bc70ba3-cf43-4015-ae71-2e93269726f0" />

- `AZURE_SUBSCRIPTION_ID` → **Subscription ID** da assinatura
  - <img width="1293" height="263" alt="image" src="https://github.com/user-attachments/assets/eeacd714-8a00-4fde-a217-8da4d8af1e3f" />



---


## Segredos no GitHub

Quando você cria segredos em Settings → Secrets and variables → Actions, eles não ficam visíveis para ninguém, mesmo que seu repositório seja público.

<img width="1406" height="852" alt="image" src="https://github.com/user-attachments/assets/0769ff1e-9cf4-4852-b17f-8f49bff60da7" />

- Esses valores são criptografados e só podem ser usados dentro dos workflows do GitHub Actions.
- O arquivo YAML dentro dele você só referencia os segredos com secrets.AZURE_CLIENT_ID, secrets.AZURE_TENANT_ID, etc.
- Isso significa que quem olhar o repositório vai ver apenas os nomes dos segredos, nunca os valores reais.


## GitHub Actions

- No seu repositório, crie a pasta: .github/workflows/
- Dentro dela, crie um arquivo YAML, por exemplo: azure-webapps.yml
- Cole o conteúdo do workflow ajustado com os segredos que você já configurou:

```yaml
name: Build and deploy ASP.Net Core app to Azure Web App - Serilog

on:
  push:
    branches:
      - master
  workflow_dispatch:

jobs:
  build:
    runs-on: windows-latest
    steps:
      - uses: actions/checkout@v4

      - name: Set up .NET Core
        uses: actions/setup-dotnet@v4
        with:
          dotnet-version: '8.x'

      - name: Build with dotnet
        run: dotnet build --configuration Release

      - name: dotnet publish
        run: dotnet publish -c Release -o "${{env.DOTNET_ROOT}}/myapp"

      - name: Upload artifact for deployment job
        uses: actions/upload-artifact@v4
        with:
          name: .net-app
          path: ${{env.DOTNET_ROOT}}/myapp

  deploy:
    runs-on: windows-latest
    needs: build
    steps:
      - name: Download artifact from build job
        uses: actions/download-artifact@v4
        with:
          name: .net-app
      
      - name: Login to Azure
        uses: azure/login@v2
        with:
          client-id: ${{ secrets.AZURE_CLIENT_ID }}
          tenant-id: ${{ secrets.AZURE_TENANT_ID }}
          subscription-id: ${{ secrets.AZURE_SUBSCRIPTION_ID }}

      - name: Deploy to Azure Web App
        uses: azure/webapps-deploy@v3
        with:
          app-name: 'Serilog'   # nome exato do seu App Service d
          slot-name: 'Production'
          package: .





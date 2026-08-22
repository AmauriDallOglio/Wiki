# Observabilidade em Arquitetura .NET com Prometheus e Grafana

## Contexto da Arquitetura

Este projeto segue uma arquitetura de microserviços em .NET, com autenticação centralizada via JWT e um frontend integrador (Maia/BFF).
Cada serviço expõe métricas via /metrics para serem coletadas pelo Prometheus e visualizadas no Grafana.

* Serviços monitorados
  * AutenticadorJwt = autenticação e autorização centralizada.
  * Maia (Frontend/BFF) = gateway único para o usuário.
  * Ollama (IA local) = inteligência artificial offline.
  * Email (Backend) = envio de mensagens.
  * Dropbox (Backend) = manipulação de arquivos.
  * Financeiro (Backend) = gestão financeira.
  * Prometheus = coleta de métricas.
  * Grafana = visualização e dashboards.

Para monitorar os resultados implentados (timeouts, retries e fallbacks), precisa expor essas informações como logs, métricas e traces. Isso permite acompanhar em tempo real no Grafana.

Instalar pacotes:
* dotnet add package OpenTelemetry.Extensions.Hosting
* dotnet add package OpenTelemetry.Instrumentation.AspNetCore
* dotnet add package OpenTelemetry.Instrumentation.Http
* dotnet add package OpenTelemetry.Exporter.Prometheus.AspNetCore
* <img width="1739" height="641" alt="image" src="https://github.com/user-attachments/assets/9faf8de9-6ae4-4ba3-9fcb-0e19d904b906" />

Configuração nos projetos:
* <img width="1676" height="697" alt="image" src="https://github.com/user-attachments/assets/974acd67-9360-4f7a-afde-e957956e499e" />

Mapeamento de métricas para tratamento de erros:
<img width="1787" height="520" alt="image" src="https://github.com/user-attachments/assets/2321b08e-315b-407a-9937-6d6fcc86094f" />


Resultado
* O Prometheus coleta métricas acessando http://localhost:5000/metrics.
* Métricas disponíveis:
  * http_server_request_duration_seconds (latência das requisições)
  * http_client_request_duration_seconds (latência das chamadas externas)
  * http_server_requests_total (quantidade de requisições)
  * http_client_requests_total (quantidade de chamadas externas)


## Prometheus

* É uma ferramenta de monitoramento e coleta de métricas.
* Funciona como um “radar”: ele acessa periodicamente os endpoints /metrics dos seus serviços e guarda os dados.
* Esses dados podem ser coisas como:
  * Quantidade de requisições recebidas.
  * Tempo de resposta (latência).
  * Uso de CPU e memória.
  * Status de disponibilidade (UP/DOWN).
* Benefício: você consegue entender o comportamento dos seus sistemas em tempo real, detectar falhas e prever gargalos.

O Prometheus não funciona como um “mensageiro” que recebe texto arbitrário. Ele só coleta métricas expostas pela sua API em um formato específico. Então, quando você fala em “enviar uma mensagem de teste”, o equivalente seria expor uma métrica personalizada na sua API e depois verificar se o Prometheus consegue coletar.

Para usar o Prometheus você precisa instalar e rodar o servidor Prometheus separadamente, ele não vem junto com o .NET. O que o AddPrometheusExporter() faz é expor as métricas da sua aplicação em um endpoint HTTP (/metrics). O Prometheus é quem vai coletar esses dados periodicamente e armazenar para consulta.

Na API você precisa liberar o endpoint /metrics da autenticação JWT e garantir que o Prometheus Exporter está configurado, o que está acontecendo é que o seu endpoint /metrics ainda está passando pelo middleware de autenticação JWT e devolvendo JSON de erro. O Prometheus só entende texto plano no formato de métricas, então precisamos garantir duas coisas na API,

Baixe o Prometheus em [prometheus.io/download](https://prometheus.io/download).

Defina a pasta para gerenciar os arquivos no meu caso destinei em: C:\Prometheus
<img width="1319" height="292" alt="image" src="https://github.com/user-attachments/assets/5e264554-2d93-41d3-a241-5cb14769992c" />

É necessário ativar o serviço no servidor pelo executavél: prometheus.exe
<img width="1287" height="255" alt="image" src="https://github.com/user-attachments/assets/ab84f288-6da3-465c-a721-edb2dede263d" />

Para testar acesso o endereço do servidor: http://localhost:9090/targets caso aparece na tela apareca a mensagem "Não é possível aceder a este site" valide se o arquivo .exe foi executado.
<img width="1512" height="519" alt="image" src="https://github.com/user-attachments/assets/15dc3a80-1160-41ec-9dbd-721d391d2cff" />

Com o processo configurados os serviços devem ser apresentados dessa forma:
<img width="1902" height="850" alt="image" src="https://github.com/user-attachments/assets/beaf2867-63f0-4917-baa9-dcfce6aa9b39" />


Crie o arquivo prometheus.yml com os jobs dos serviços: O prometheus.yml atual está configurado apenas para o próprio Prometheus (localhost:9090). Se você quer que ele coletemétricas da sua API .NET, precisa adicionar um novo scrape_config apontando para o endpoint /metrics da sua aplicação.

<img width="1597" height="752" alt="image" src="https://github.com/user-attachments/assets/24e65b66-b82c-40dd-8256-4475f9cce6f9" />

* Se a sua API está rodando em http://localhost:5135/swagger/index.html, isso significa que ela está exposta na porta 5135. Para o Prometheus conseguir coletar métricas, você precisa ajustar o prometheus.yml para apontar para essa porta e para o endpoint /metrics (que é onde o OpenTelemetry expõe os dados).

Se você tem outro serviço rodando e quer que o Prometheus monitore esse serviço também, o que precisa ser feito é adicionar mais um scrape job no arquivo prometheus.yml. Exemplo abaixo:

```text
global:
  scrape_interval: 15s
  evaluation_interval: 15s

scrape_configs:
  # Prometheus monitorando a si mesmo
  - job_name: "prometheus"
    static_configs:
      - targets: ["localhost:9090"]
        labels:
          app: "prometheus"

  # Autenticador JWT
  - job_name: "autenticacaojwt"
    scrape_interval: 5s
    static_configs:
      - targets: ["localhost:5135"]
        labels:
          app: "autenticacaojwt"

  # Maia (Frontend BFF)
  - job_name: "maia"
    scrape_interval: 5s
    static_configs:
      - targets: ["localhost:5173"]
        labels:
          app: "maia"

  # Ollama (IA local)
  - job_name: "ollama"
    scrape_interval: 5s
    static_configs:
      - targets: ["localhost:5140"]
        labels:
          app: "ollama"

  # Email (Backend)
  - job_name: "email"
    scrape_interval: 5s
    static_configs:
      - targets: ["localhost:5035"]
        labels:
          app: "email"

  # Dropbox (Backend)
  - job_name: "dropbox"
    scrape_interval: 5s
    static_configs:
      - targets: ["localhost:5137"]
        labels:
          app: "dropbox"

  # Financeiro (Backend)
  - job_name: "financeiro"
    scrape_interval: 5s
    static_configs:
      - targets: ["localhost:5057"]
        labels:
          app: "financeiro"

  # PrometheusNet (Backend)
  - job_name: "prometheusNet"
    scrape_interval: 5s
    static_configs:
      - targets: ["localhost:5169"]
        labels:
          app: "prometheusNet"

   # Autenticador JWT IIS
  - job_name: "autenticacaojwt iis"
    scrape_interval: 5s
    static_configs:
      - targets: ["localhost:5002"]
        labels:
          app: "autenticacaojwt"

  # Ollama IIS
  - job_name: "ollama iis"
    scrape_interval: 5s
    static_configs:
      - targets: ["localhost:5003"]
        labels:
          app: "ollama"

  # Dropbox IIS
  - job_name: "dropbox iis"
    scrape_interval: 5s
    static_configs:
      - targets: ["localhost:5004"]
        labels:
          app: "dropbox"

  # Financeiro IIS
  - job_name: "financeiro iis"
    scrape_interval: 5s
    static_configs:
      - targets: ["localhost:5005"]
        labels:
          app: "financeiro"

```




Para rodar todos os serviços (Prometheus e Grafana) poderá criar um arquivo bat:

```text
@echo off
cd /d C:\Prometheus
echo Iniciando Prometheus...
start prometheus.exe --config.file=prometheus.yml
timeout /t 5 >nul
start http://localhost:9090/targets
start http://localhost:3000/d/adpxkgd/autenticacao-jwt?orgId=1&from=now-6h&to=now&timezone=browser
pause

```


 
Se você tem outro serviço rodando e quer que o Prometheus monitore esse serviço também, o que precisa ser feito é adicionar mais um scrape job no arquivo prometheus.yml.


global:
  scrape_interval: 15s

scrape_configs:
  - job_name: "prometheus"
    static_configs:
      - targets: ["localhost:9090"]

  - job_name: "autenticacaojwt"
    static_configs:
      - targets: ["localhost:5135"]

  - job_name: "maia"
    static_configs:
      - targets: ["localhost:5035"]

  - job_name: "ollama"
    static_configs:
      - targets: ["localhost:5140"]

  - job_name: "email"
    static_configs:
      - targets: ["localhost:5050"]

  - job_name: "dropbox"
    static_configs:
      - targets: ["localhost:5055"]

  - job_name: "financeiro"
    static_configs:
      - targets: ["localhost:5057"]


Para o start do Prometheus no Windows sem precisar digitar os comandos manualmente no PowerShell, você pode criar um arquivo .bat. Esse arquivo vai abrir o Prometheus já com o prometheus.yml configurado.

Crie o script start-prometheus.bat:
Abra o Bloco de Notas, cole o conteúdo abaixo, salve como start-prometheus.bat dentro da pasta C:\Prometheus.  Atenção: escolha “Todos os arquivos (.)” em vez de “.txt” na hora de salvar. Dê um duplo clique no arquivo start-prometheus.bat. O Prometheus vai iniciar e abrir os logs no console.

Acesse http://localhost:9090 no navegador para confirmar.

'@echo off

cd /d C:\Prometheus

echo Iniciando Prometheus...

start prometheus.exe --config.file=prometheus.yml

timeout /t 5 >nul

start http://localhost:9090/targets

pause'



Verificar targets: 
* Acesse http://localhost:9090/targets 

<img width="1551" height="591" alt="image" src="https://github.com/user-attachments/assets/52e9cb66-3285-4c56-b09a-f3057e08f0b8" />

Você deve ver dois jobs:
* prometheus → status UP
* autenticacaojwt → status UP (se sua API estiver rodando e expondo métricas).




## Grafana

* É uma plataforma de visualização de dados.
* Ele se conecta ao Prometheus (que coleta os dados) e transforma em gráficos, dashboards e alertas.
* Benefício: em vez de olhar números crus, você vê painéis visuais que facilitam a análise e tomada de decisão.
* Exemplo: um gráfico mostrando a latência p95 do serviço Financeiro ou um gauge mostrando se o AutenticadorJwt está UP ou DOWN.

### Para que servem os Dashboards

* São painéis visuais que mostram métricas importantes de cada aplicação.
* Com dashboards você pode:
  * Monitorar disponibilidade (se o serviço está UP/DOWN).
  * Acompanhar tráfego (quantas requisições cada serviço recebe).
  * Medir latência (tempo de resposta).
  * Ver consumo de recursos (CPU, memória).
  * Criar alertas (ex.: se o serviço cair ou se a latência passar de 2 segundos).

### Por que tantas aplicações?

* Em uma arquitetura moderna de microserviços em .NET, cada aplicação tem uma responsabilidade única:
  * AutenticadorJwt = autenticação centralizada.
  * Maia (BFF) = frontend integrador.
  * Ollama = IA local.
  * Email = envio de mensagens.
  * Dropbox = manipulação de arquivos.
  * Financeiro = gestão financeira.
* Benefício: desacoplamento. Cada serviço pode evoluir, escalar ou ser substituído sem impactar os outros.
* O Prometheus + Grafana entram como observabilidade centralizada, monitorando todos esses serviços em conjunto.

 
Rode o servidor (grafana-server.exe).
* Baixe o Grafana em [grafana.com](https://grafana.com/grafana/download).
* Instale e rode o servidor (grafana-server.exe).
* Rode o servidor (grafana-server.exe).
* Acesse http://localhost:3000
  * Usuário padrão: admin
  * Senha padrão: admin (vai pedir para trocar na primeira vez).
* Configure o Prometheus como Data Source:
  * URL: http://localhost:9090
  * Clique em Save & Test.

### Conectar o Grafana ao Prometheus

No Grafana, vá em Configuration > Data Sources.
Clique em Add data source.
Escolha Prometheus.
onfigure a URL: http://localhost:9090

<img width="1440" height="675" alt="image" src="https://github.com/user-attachments/assets/b46158d7-150b-4c0a-a7ca-248389cbf34e" />

Se tudo estiver certo, o Grafana confirma a conexão.

<img width="1259" height="273" alt="image" src="https://github.com/user-attachments/assets/d1e9f5f7-e707-487d-b889-988295a5c040" />


<img width="1467" height="674" alt="image" src="https://github.com/user-attachments/assets/e9921f39-3217-48ff-a336-dac93d5846eb" />


## Dashboards no Grafana

Para montar dashboards no Grafana, você precisa saber quais métricas estão disponíveis nos seus serviços instrumentados com OpenTelemetry + Prometheus. Aqui vai uma lista prática das métricas mais comuns que você pode usar:

<img width="1277" height="848" alt="image" src="https://github.com/user-attachments/assets/aa11d255-534d-4f26-8d82-1261ddea380b" />


Métricas principais para .NET

<img width="1839" height="812" alt="image" src="https://github.com/user-attachments/assets/c47522d5-6f7a-4dca-baec-81236394ef44" />


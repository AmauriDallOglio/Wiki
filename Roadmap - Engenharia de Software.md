# Engenharia de Software

> Guia prático para Engenharia de Software Moderna utilizando .NET, Arquitetura de Software, Cloud Computing, DevOps e Inteligência Artificial.

---

# Roadmap

- ✅ Fundamentos da Linguagem
- ✅ Princípios de Engenharia de Software
- ✅ Arquitetura de Software
- ✅ Persistência de Dados
- ✅ APIs Modernas
- ✅ Testes e Qualidade
- ✅ Observabilidade
- ✅ Segurança
- ✅ Containers e DevOps
- ✅ Sistemas Distribuídos
- ✅ Inteligência Artificial
- ✅ Governança Técnica

---

# 1 Fundamentos do C#

## 1.1 Sintaxe e Tipos de Dados
- [ ] Tipos Primitivos
- [ ] Structs
- [ ] Enums
- [ ] Records
- [ ] Nullable Reference Types
- [ ] Arrays
- [ ] Span<T> / Memory<T>

## 1.2 Programação Orientada a Objetos
- [ ] Encapsulamento
- [ ] Herança
- [ ] Polimorfismo
- [ ] Abstração
- [ ] Interfaces
- [ ] Classes
- [ ] Classes Abstratas
- [ ] Classes Estáticas
- [ ] Classes Parciais
- [ ] Records

## 1.3 Recursos Avançados
- [ ] Generics
- [ ] Delegates
- [ ] Events
- [ ] Expression Trees
- [ ] Reflection
- [ ] Attributes
- [ ] Source Generators

## 1.4 LINQ
- [ ] LINQ to Objects
- [ ] LINQ to Entities
- [ ] Expressões Lambda
- [ ] Métodos de Extensão

## 1.5 Concorrência
- [ ] async/await
- [ ] Task
- [ ] Parallel
- [ ] TPL
- [ ] SemaphoreSlim
- [ ] Channels
- [ ] CancellationToken

## 1.6 Tratamento de Erros
- [ ] try/catch/finally
- [ ] Exceções Customizadas
- [ ] Global Exception Handler

---

# 2 Engenharia de Software

## 2.1 Princípios
- [ ] SOLID
- [ ] Clean Code
- [ ] Clean Architecture
- [ ] DRY
- [ ] KISS
- [ ] YAGNI
- [ ] Fail Fast

## 2.2 Design Patterns (GoF)
- [ ] Singleton
- [ ] Factory
- [ ] Builder
- [ ] Strategy
- [ ] Observer
- [ ] Decorator
- [ ] Adapter
- [ ] Facade
- [ ] Repository

## 2.3 Domain-Driven Design
- [ ] Entidades
- [ ] Value Objects
- [ ] Aggregates
- [ ] Domain Events
- [ ] Repositories
- [ ] Bounded Context
- [ ] Ubiquitous Language

## 2.4 Arquiteturas
- [ ] Clean Architecture
- [ ] Onion Architecture
- [ ] Hexagonal
- [ ] Vertical Slice
- [ ] Modular Monolith
- [ ] Layered Architecture

## 2.5 CQRS
- [ ] Commands
- [ ] Queries
- [ ] MediatR
- [ ] Pipeline Behavior

---

# 3 Arquitetura de Software

## Arquiteturas
- [ ] Clean Architecture
- [ ] Onion
- [ ] Hexagonal
- [ ] Vertical Slice
- [ ] Microsserviços

## Arquiteturas Distribuídas
- [ ] Microsserviços
- [ ] API Gateway
- [ ] Backend for Frontend (BFF)
- [ ] Service Discovery
- [ ] Event Driven
- [ ] Event Sourcing
- [ ] Saga Pattern
- [ ] Outbox Pattern

## Modelagem
- [ ] C4 Model
- [ ] UML
- [ ] TOGAF
- [ ] ADR (Architecture Decision Records)

### Arquitetura da API
- [ ] Clean Architecture
- [ ] Regras independentes de framework
- [ ] Comunicação REST
- [ ] Separação de responsabilidades
- [ ] Restringir CORS por ambiente  
- [ ] Garantir HTTPS/HSTS em produção  
- [ ] Reativar autenticação/autorização nos endpoints  
- [ ] Remover segredos de `appsettings.json`  
- [ ] Padronizar respostas HTTP  
- [ ] Adicionar versionamento de API  
- [ ] Criar correlation ID por requisição  
- [ ] Melhorar logs estruturados  
- [ ] Configurar resiliência com Polly  
- [ ] Adicionar health checks  
- [ ] Criar testes automatizados (controllers, pipeline, jobs)  
- [ ] Validar entradas com FluentValidation  
- [ ] Documentar decisões arquiteturais (ADRs)  
- [ ] Middleware centralizado de erros  
- [ ] Suporte a Docker e IIS  
- [ ] Swagger/OpenAPI configurado  
- [ ] Endpoint de métricas Prometheus  
- [ ] Configuração tipada e organizada  

### Camadas

- [ ] Domain
- [ ] Application
- [ ] Infrastructure
- [ ] Presentation/API

### Padrões

- [ ] CQRS
- [ ] DDD
- [ ] Repository Pattern
- [ ] API Gateway
- [ ] Hangfire
- [ ] MediatR
- [ ] SignalR
- [ ] Application Insights

## DDD

- [ ] Entidades
- [ ] Value Objects
- [ ] Aggregates
- [ ] Domain Events
- [ ] Bounded Context

## CQRS

- [ ] Commands
- [ ] Queries
- [ ] MediatR
- [ ] Pipeline Behavior

---

# 4 APIs Modernas

## ASP.NET Core
- [ ] Controllers
- [ ] Minimal API
- [ ] Middleware

## REST
- [ ] HTTP
- [ ] Versionamento
- [ ] Swagger/OpenAPI
- [ ] HATEOAS

## Segurança
- [ ] JWT
- [ ] OAuth2
- [ ] OpenID Connect
- [ ] Identity
- [ ] Claims
- [ ] Policies
- [ ] HTTPS
- [ ] HSTS
- [ ] CORS
- [ ] CSP
- [ ] XSS
- [ ] CSRF
- [ ] SQL Injection
- [ ] Rate Limiting
- [ ] Secrets Management

---

# 5 Persistência

## Banco Relacional
- [ ] SQL Server
- [ ] PostgreSQL
- [ ] MySQL

## Modelagem
- [ ] Relacionamentos
- [ ] Índices
- [ ] Normalização
- [ ] Procedures
- [ ] Views

## NoSQL
- [ ] MongoDB
- [ ] Redis

## ORM
- [ ] Entity Framework Core
- [ ] Dapper

## Entity Framework Core
- [ ] Code First
- [ ] Database First
- [ ] Migrations
- [ ] Fluent API

## Dapper
- [ ] CRUD
- [ ] Queries Performáticas

## Performance
- [ ] Lazy Loading
- [ ] Eager Loading
- [ ] Split Queries
- [ ] Compiled Queries

## Cache
- [ ] Memory Cache
- [ ] Redis
- [ ] Distributed Cache

---

# 6. Desenvolvimento Web
- [ ] Blazor
- [ ] SignalR
- [ ] Razor Pages
- [ ] React
- [ ] Angular
- [ ] Tag Helpers

---

# 7 Testes
## Automatizados
- [ ] xUnit
- [ ] NUnit
- [ ] MSTest

## Qualidade
- [ ] TDD
- [ ] BDD
- [ ] Mock
- [ ] Integração
- [ ] End-to-End
- [ ] Performance (k6)
- [ ] Benchmark.NET

---

# 8 Observabilidade

## Logs
- [ ] Serilog
- [ ] ILogger

## Métricas
- [ ] Prometheus
- [ ] Grafana

## Telemetria
- [ ] OpenTelemetry
- [ ] Application Insights

## Monitoramento
- [ ] Application Insights
- [ ] Health Checks

---

# 9 Performance

## Resiliência
- [ ] Polly
- [ ] Retry
- [ ] Timeout
- [ ] Circuit Breaker
- [ ] Bulkhead
- [ ] Fallback

## Performance
- [ ] Benchmark.NET
- [ ] Profiling

---

# 10 Containers & Cloud

## Containers
- [ ] Docker
- [ ] Docker Compose

## Kubernetes
- [ ] Pods
- [ ] Services
- [ ] Deployments
- [ ] Ingress

## Azure
- [ ] App Service
- [ ] Azure SQL
- [ ] Azure Storage
- [ ] Azure Functions
- [ ] Azure Service Bus
- [ ] Azure Key Vault
- [ ] Azure Monitor

---

# 11 DevOps

## Git
- [ ] Git Flow
- [ ] Pull Request
- [ ] Code Review

## CI/CD
- [ ] GitHub Actions
- [ ] Azure DevOps
- [ ] Jenkins

## Infraestrutura
- [ ] IaC
- [ ] Bicep
- [ ] Terraform

---

# 12 Sistemas Distribuídos

## Mensageria
- [ ] RabbitMQ
- [ ] Kafka
- [ ] Azure Service Bus

## Arquitetura
- [ ] Event Driven
- [ ] Saga
- [ ] Outbox Pattern

## Frameworks
- [ ] MassTransit
- [ ] Dapr

---

# 13 Inteligência Artificial

## Machine Learning
- [ ] ML.NET

## LLM
- [ ] Ollama
- [ ] OpenAI
- [ ] Gemma

## IA Generativa
- [ ] Prompt Engineering
- [ ] RAG
- [ ] Embeddings
- [ ] Vector Database

## AI Engineering
- [ ] Semantic Kernel
- [ ] AI Agents
- [ ] MCP (Model Context Protocol)
- [ ] Function Calling

---

# 14 Governança Técnica

## Documentação
- [ ] README
- [ ] ADR
- [ ] Diagramas C4
- [ ] UML
- [ ] OpenAPI

## Desenvolvimento
- [ ] Coding Standards
- [ ] Code Review
- [ ] Checklist de Desenvolvimento
- [ ] Definition of Done
- [ ] Git Flow

## Qualidade
- [ ] SonarQube
- [ ] Cobertura de Testes
- [ ] Security Scan
- [ ] Dependabot
- [ ] SAST
- [ ] DAST

---

# 15 Checklist de Desenvolvimento

- [ ] Planejamento
- [ ] Levantamento de Requisitos
- [ ] Modelagem
- [ ] Arquitetura
- [ ] Desenvolvimento
- [ ] Testes
- [ ] Documentação
- [ ] Deploy
- [ ] Monitoramento
- [ ] Evolução Contínua


# 16 Plano de Estudo Avançado (.NET 8 & Arquitetura Moderna)

- [ ] Fundamentos C# e OOP  
- [ ] Padrões de projeto (GOF, DDD, CQRS)  
- [ ] Arquiteturas modernas (Clean, Hexagonal, Microsserviços, Event-Driven)  
- [ ] Persistência (SQL, NoSQL, EF Core, Dapper)  
- [ ] Testes (unitários, integração, carga)  
- [ ] Observabilidade (Serilog, Prometheus, OpenTelemetry)  
- [ ] Resiliência (Polly, Circuit Breaker)  
- [ ] DevOps (Docker, CI/CD, Azure Pipelines)  
- [ ] Mensageria (RabbitMQ, Kafka, Azure Service Bus)  
- [ ] APIs modernas com .NET 8  
- [ ] Desenvolvimento Web (Blazor, SignalR)  
- [ ] Concorrência e Background Jobs  

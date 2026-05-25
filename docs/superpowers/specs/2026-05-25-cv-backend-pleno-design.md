# CV Backend Pleno — Design Spec

**Data:** 2026-05-25  
**Arquivo de saída:** `index-backend-pleno.html`  
**Base:** `index.html` (layout e toggle PT/EN mantidos)

---

## Contexto

Nélio Dias precisa de um CV direcionado a uma vaga de **Desenvolvedor Backend Pleno** com foco em Python. O CV atual (`index.html`) posiciona-o como Full-Stack Sênior, o que dilui o sinal backend. A solução é criar um novo arquivo com curadoria focada em backend Python.

---

## Abordagem Escolhida

**Curadoria Focada (Abordagem 1):** remover experiências puramente frontend, reescrever bullets para enfatizar backend, adicionar o projeto FastAPI (Esthetic Fast Scheduler), reordenar tecnologias com Python ecosystem em destaque.

---

## Estrutura do Arquivo

```
index-backend-pleno.html
├── <head> — meta tags, estilos, toggle script (igual ao index.html)
├── Header — nome
├── Contato — igual ao atual
├── Resumo / Summary — reescrito para Backend Pleno Python
├── Tecnologias / Technologies — reorganizado (Python first)
├── Experiência Profissional / Professional Experience
│   ├── 1. Esthetic Fast Scheduler — Cliente (2026)
│   ├── 2. ALLM — Backend SaaS (2025–2026)
│   ├── 3. Startamus Pleno — Backend (OUT/2022–2024)
│   ├── 4. Gotech DS (MAI/2022–OUT/2022)
│   └── 5. UFPA (AGO/2021–JAN/2022)
└── Educação / Education — igual ao atual
```

**Removidos:** Startamus/Nuuvem (gaming frontend SvelteKit) e Startamus/P4F (checkout React) — 100% frontend, não agregam para a vaga.

---

## Resumo / Summary

**PT:**
Desenvolvedor Backend Pleno com 4+ anos de experiência construindo APIs e sistemas distribuídos em produção. Especialista em Python (FastAPI, Django) com foco em arquiteturas orientadas a eventos, processamento assíncrono e integração de serviços externos. Experiência sólida com PostgreSQL, Docker, AWS (Lambda, ECS, SQS) e observabilidade. Fluência operacional em IA aplicada ao desenvolvimento (Claude Code, GitHub Copilot). Histórico de entrega em squads ágeis com code review, CI/CD e testes automatizados.

**EN:**
Mid-level Backend Developer with 4+ years building APIs and distributed systems in production. Specialized in Python (FastAPI, Django) with focus on event-driven architectures, async processing, and external service integration. Solid experience with PostgreSQL, Docker, AWS (Lambda, ECS, SQS), and observability. Operational fluency in AI-assisted development (Claude Code, GitHub Copilot). Track record of delivery in agile squads with code review, CI/CD, and automated testing.

---

## Tecnologias

Grade de 12 colunas, reordenada:

```
Python      FastAPI      Django       Node.js      NestJS       Express
PostgreSQL  SQLAlchemy   Redis        SQLite       Prisma ORM   REST APIs
AWS Lambda  AWS ECS      AWS S3       AWS SQS      Docker       Kubernetes
RabbitMQ    OpenTelemetry Pytest      Jest         Ruff         CI/CD
Claude Code GitHub Copilot Git        TypeScript   React        JavaScript
```

**Entram:** FastAPI, SQLAlchemy, RabbitMQ, Pytest, Ruff, Claude Code, GitHub Copilot, Kubernetes  
**Saem:** SvelteKit, Tailwind, Java, Spring Boot, i18n, Firebase, Vitest, Playwright

---

## Experiências

### 1. Esthetic Fast Scheduler — Cliente (2026)
**Título PT:** Desenvolvedor Backend Python — Cliente  
**Título EN:** Backend Python Developer — Client Project

Bullets PT:
- Desenvolvi backend em **FastAPI** para automação de agendamentos via WhatsApp para studios de estética, com arquitetura multi-tenant e integração com Evolution API.
- Modelei banco de dados relacional com **SQLAlchemy 2.0 + PostgreSQL** (tenants, clientes, conversas, serviços, horários, agendamentos) e versionei com Alembic.
- Implementei **webhook de mensagens WhatsApp** com parser de payloads, deduplicação por mensagem, resolução de identidade WhatsApp/LID e máquina de estados persistida para conduzir o fluxo conversacional.
- Criei **motor de disponibilidade** considerando horário comercial, bloqueios manuais, duração total de múltiplos serviços, buffer entre atendimentos e conflitos com agendamentos pendentes.
- Apliquei boas práticas: testes automatizados com **Pytest**, linting com **Ruff**, logs estruturados em JSON, rate limiting em memória, migrações versionadas e configuração por variáveis de ambiente.

Bullets EN:
- Built a **FastAPI** backend for WhatsApp-based appointment automation for aesthetic studios, with multi-tenant architecture and Evolution API integration.
- Modeled relational database with **SQLAlchemy 2.0 + PostgreSQL** (tenants, clients, conversations, services, schedules, bookings) versioned with Alembic.
- Implemented **WhatsApp message webhook** with payload parsing, message deduplication, WhatsApp/LID identity resolution, and persisted state machine to drive conversational flow.
- Created **availability engine** considering business hours, manual blocks, total duration of multiple services, buffer between appointments, and conflicts with pending bookings.
- Applied best practices: automated testing with **Pytest**, linting with **Ruff**, structured JSON logs, in-memory rate limiting, versioned migrations, and environment-based configuration.

**Stack:** Python 3.12, FastAPI, SQLAlchemy 2.0, Alembic, PostgreSQL, Redis, Docker Compose, Pytest, Ruff, Poetry

---

### 2. ALLM — Backend SaaS Médico (2025–2026)
**Título PT:** Desenvolvedor Backend Sênior — ALLM (Plataforma SaaS Médica)  
**Título EN:** Senior Backend Developer — ALLM (Medical SaaS Platform)

Bullets PT:
- Projetei e implementei o **backend completo de uma plataforma SaaS B2B multi-tenant** para comunidades médicas em NestJS 11 + TypeScript, com APIs REST para fóruns, casos clínicos com schema dinâmico e notificações push multi-plataforma.
- Arquitetei sistema de **autorização granular por comunidade** com 5 papéis hierárquicos, RBAC via guards compostos e **audit trail forense** — garantindo isolamento de dados entre tenants e conformidade LGPD.
- Implementei **pipeline assíncrono de processamento de mídia** via AWS Lambda com anonimização automática de imagens DICOM (remoção de PHI) e status tracking via SQS.
- Estruturei **CI/CD em GitHub Actions** com Docker multi-stage, migrations isoladas em Fargate, deploy zero-downtime em ECS e injeção dinâmica de secrets por ambiente.
- Configurei **observabilidade** com OpenTelemetry + Winston estruturado para rastreamento distribuído em produção; escrevi 68 suites de testes com 73K+ LOC de regras de negócio.

Bullets EN:
- Designed and implemented the **full backend of a B2B multi-tenant medical SaaS platform** with NestJS 11 + TypeScript, REST APIs for forums, clinical cases with dynamic schema, and multi-platform push notifications.
- Architected a **per-community layered authorization system** with 5 hierarchical roles, composed guards RBAC, and **forensic audit logging** — enforcing data isolation between tenants and LGPD compliance.
- Built **async media processing pipeline** via AWS Lambda with automated DICOM image anonymization (PHI removal) and async status tracking via SQS.
- Structured **CI/CD in GitHub Actions** with multi-stage Docker, isolated Fargate migrations, zero-downtime ECS deployments, and dynamic secret injection per environment.
- Configured **observability** with OpenTelemetry + structured Winston logging for distributed tracing in production; wrote 68 test suites with 73K+ LOC of business rule specs.

---

### 3. Startamus Pleno — Backend (OUT/2022–2024)
**Título PT:** Desenvolvedor Backend Pleno — Startamus  
**Título EN:** Mid Backend Developer — Startamus

Bullets PT:
- Gerenciei time de backend no desenvolvimento de **RESTful APIs com Django REST Framework**, estabelecendo padrões de código, coordenando code reviews e garantindo alta performance.
- Arquitetei integrações críticas com **AWS S3**, Twilio (SMS, WhatsApp, email) e **PostgreSQL**, garantindo uptime e segurança dos dados.
- Liderei modernização de sistema legado implementando **clean code e design patterns**, resultando em redução de 40% no tempo de carregamento e aumento de 25% na taxa de conversão.
- Coordenei equipes multidisciplinares com metodologias ágeis (Scrum/Kanban) e práticas de integração contínua.

Bullets EN:
- Managed backend team developing **RESTful APIs with Django REST Framework**, establishing coding standards, coordinating code reviews, and ensuring high performance.
- Architected critical integrations with **AWS S3**, Twilio (SMS, WhatsApp, email), and **PostgreSQL**, ensuring uptime and data security.
- Led legacy system modernization implementing **clean code and design patterns**, resulting in 40% reduction in load time and 25% increase in conversion rate.
- Coordinated cross-functional teams using agile methodologies (Scrum/Kanban) and continuous integration practices.

---

### 4. Gotech DS (MAI/2022–OUT/2022)
**Título PT:** Desenvolvedor Full-Stack — Gotech DS  
**Título EN:** Full-Stack Developer — Gotech DS

Bullets (enxutos, foco em backend):
- PT: Desenvolvi plataforma de e-commerce com **16.000 usuários**, autenticação JWT, múltiplos níveis de acesso, **PostgreSQL** e Docker em ambiente remoto com Git Flow.
- EN: Built e-commerce platform with **16,000 users**, JWT authentication, multiple access levels, **PostgreSQL**, and Docker in a remote Git Flow environment.

---

### 5. UFPA (AGO/2021–JAN/2022)
**Título PT:** Desenvolvedor — UFPA  
**Título EN:** Developer — UFPA

Bullets (mantém foco no Python):
- PT: Desenvolvi **LABVCON v2.0** em **Python + Streamlit** para aplicação de controladores avançados em protótipos Arduino com monitoramento de dados em tempo real.
- EN: Built **LABVCON v2.0** in **Python + Streamlit** for applying advanced controllers on Arduino prototypes with real-time data monitoring.

---

## Educação

Igual ao `index.html`:
- Inglês Avançado C1 (link para certificado)
- Análise e Desenvolvimento de Sistemas — Gran Faculdade
- Engenharia de Controle e Automação — IFPA Campus Belém

---

## Alinhamento com a Vaga

| Requisito da Vaga | Cobertura no CV |
|---|---|
| Python 3.10+ em produção | FastAPI (Python 3.12) + Django |
| REST APIs | ALLM, FastAPI, Startamus |
| PostgreSQL | FastAPI, ALLM, Startamus, Gotech |
| Processamento assíncrono | AWS Lambda + SQS (ALLM), máquina de estados (FastAPI) |
| Git + PR/code review | Startamus, ALLM |
| Docker | ALLM, FastAPI, Gotech |
| IA aplicada (Claude Code, Copilot) | Resumo + lista de tech |
| Mensageria (SQS) | ALLM (Lambda + SQS) |
| AWS Lambda, S3, SQS, ECS | ALLM |
| Kubernetes | Lista de tech |
| Node.js | Lista de tech |
| Observabilidade | ALLM (OpenTelemetry + Winston), FastAPI (JSON logs) |
| Testes automatizados | ALLM (68 suites Jest), FastAPI (Pytest) |

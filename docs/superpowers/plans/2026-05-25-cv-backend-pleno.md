# CV Backend Pleno — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Criar `index-backend-pleno.html` — CV direcionado à vaga de Desenvolvedor Backend Pleno Python, bilíngue PT/EN, com curadoria focada em backend.

**Architecture:** Single HTML file com toggle PT/EN (mesmo padrão de `index.html`). Estrutura: head/styles, header, contato, resumo, tecnologias, 5 experiências (FastAPI client, ALLM, Startamus Pleno, Gotech, UFPA), educação. Sem dependências externas além do Google Fonts.

**Tech Stack:** HTML5, CSS (inline), JavaScript (toggle), Google Fonts (Epilogue)

---

### Task 1: Criar arquivo base com head, estilos e script

**Files:**
- Create: `index-backend-pleno.html`

- [ ] **Step 1: Criar o arquivo com head completo**

```html
<!DOCTYPE html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta name="description" content="Nélio Dias - Desenvolvedor Backend Pleno com 4+ anos de experiência em Python, FastAPI, Django, PostgreSQL e AWS. Especialista em APIs REST, processamento assíncrono e arquiteturas distribuídas." />
    <meta name="keywords" content="desenvolvedor backend, Python, FastAPI, Django, PostgreSQL, AWS, Docker, REST API, desenvolvedor backend pleno" />
    <meta name="author" content="Nélio Dias" />
    <meta name="robots" content="index, follow" />
    <meta property="og:title" content="Nélio Dias - Desenvolvedor Backend Pleno" />
    <meta property="og:description" content="Desenvolvedor Backend Pleno com 4+ anos de experiência em Python, FastAPI, Django e AWS." />
    <meta property="og:type" content="profile" />
    <meta property="og:url" content="https://nelio-dias-portfolio.vercel.app/" />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link href="https://fonts.googleapis.com/css2?family=Epilogue:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet" />
    <title>Nélio Dias - Desenvolvedor Backend Pleno | Python, FastAPI, Django, PostgreSQL</title>
    <style>
      @page {
        size: A4;
        margin: 5px;
      }

      body {
        font-family: Epilogue, Arial, sans-serif;
        padding: 5mm 10mm;
        width: 210mm;
        height: 297mm;
        margin: 0 auto;
      }

      h1, h2, h3, p {
        color: #333;
        margin: 0px;
      }

      h1 {
        font-size: 24px;
        text-align: center;
      }

      h2 {
        font-size: 18px;
        margin: 5px 0px;
      }

      h3 {
        font-size: 16px;
        margin: 5px 0px;
        font-weight: semibold;
        color: #464545;
      }

      p {
        line-height: 1.2;
        font-size: 14px;
      }

      ul {
        font-size: 14px;
        padding: 5px 15px;
        margin: 0px 0px;
      }

      li {
        margin: 5px 0;
        line-height: 1.3;
      }

      li::marker {
        margin: 2px 0px;
      }

      article {
        margin-bottom: 10px;
        margin-top: 10px;
      }

      .tech {
        display: grid;
        grid-template-columns: repeat(12, 1fr);
        margin: 0px;
        padding: 2px;
        font-size: 11px;
        list-style-type: none;
      }

      a {
        color: #1a0dab;
        text-decoration: none;
        font-size: 14px;
      }

      .contact-info {
        margin-top: 20px;
        display: flex;
        justify-content: space-between;
        width: 70%;
        margin: 0 auto;
      }

      .contact-info a {
        display: flex;
        margin-bottom: 5px;
      }

      .subsection {
        margin-bottom: 10px;
        margin-top: 10px;
      }

      .project-header {
        display: flex;
        justify-content: space-between;
        align-items: center;
      }

      .project-time {
        font-size: 12px;
      }

      .project-tech {
        font-weight: bold;
      }

      .language-switch {
        text-align: center;
        display: flex;
        justify-content: end;
      }

      .language-switch button {
        background-color: transparent;
        color: #c4c4c4;
        border: none;
        cursor: pointer;
        font-size: 10px;
      }

      .language-switch button:hover {
        text-decoration: underline;
      }
    </style>
    <script>
      function toggleLanguage() {
        const elementsPT = document.querySelectorAll(".pt");
        const elementsEN = document.querySelectorAll(".en");
        elementsPT.forEach((el) => (el.style.display = el.style.display === "none" ? "block" : "none"));
        elementsEN.forEach((el) => (el.style.display = el.style.display === "none" ? "block" : "none"));
      }
    </script>
  </head>
```

- [ ] **Step 2: Verificar que o arquivo foi criado**

```bash
ls -la /home/nelio/github/cv-nelio-dias/index-backend-pleno.html
```
Esperado: arquivo listado com tamanho > 0.

---

### Task 2: Adicionar body — header, contato e resumo

**Files:**
- Modify: `index-backend-pleno.html`

- [ ] **Step 1: Adicionar body com header, contato e resumo**

Adicionar após o `</head>`:

```html
  <body>
    <div class="language-switch">
      <button onclick="toggleLanguage()">Change Language</button>
    </div>

    <header>
      <h1 itemscope itemtype="https://schema.org/Person">
        <span itemprop="name">NÉLIO DIAS</span>
      </h1>
    </header>

    <section class="section contact-info" itemscope itemtype="https://schema.org/Person">
      <a href="https://api.whatsapp.com/send?phone=5591989079292" itemprop="telephone">(91)989079292</a>
      <a href="mailto:jrneliodias@gmail.com" itemprop="email">jrneliodias@gmail.com</a>
      <a href="https://nelio-dias-portfolio.vercel.app/" target="_blank" itemprop="url">Portfolio</a>
      <a href="https://github.com/jrneliodias" target="_blank" itemprop="sameAs">Github</a>
      <a href="https://www.linkedin.com/in/neliodias" target="_blank" itemprop="sameAs">Linkedin</a>
    </section>

    <article itemscope itemtype="https://schema.org/Person">
      <h2 class="pt">RESUMO</h2>
      <p class="pt" itemprop="description">
        Desenvolvedor Backend Pleno com 4+ anos de experiência construindo APIs e sistemas distribuídos em produção. Especialista em Python (FastAPI, Django) com foco em arquiteturas orientadas a eventos, processamento assíncrono e integração de serviços externos. Experiência sólida com PostgreSQL, Docker, AWS (Lambda, ECS, SQS) e observabilidade. Fluência operacional em IA aplicada ao desenvolvimento (Claude Code, GitHub Copilot). Histórico de entrega em squads ágeis com code review, CI/CD e testes automatizados.
      </p>

      <h2 class="en" style="display: none">SUMMARY</h2>
      <p class="en" style="display: none" itemprop="description">
        Mid-level Backend Developer with 4+ years building APIs and distributed systems in production. Specialized in Python (FastAPI, Django) with focus on event-driven architectures, async processing, and external service integration. Solid experience with PostgreSQL, Docker, AWS (Lambda, ECS, SQS), and observability. Operational fluency in AI-assisted development (Claude Code, GitHub Copilot). Track record of delivery in agile squads with code review, CI/CD, and automated testing.
      </p>
    </article>
```

---

### Task 3: Adicionar seção de tecnologias

**Files:**
- Modify: `index-backend-pleno.html`

- [ ] **Step 1: Adicionar article de tecnologias**

```html
    <article itemscope itemtype="https://schema.org/ItemList">
      <h2 class="pt" itemprop="name">TECNOLOGIAS</h2>
      <h2 class="en" style="display: none" itemprop="name">TECHNOLOGIES</h2>
      <ul class="tech" itemprop="itemListElement">
        <li>Python</li>
        <li>FastAPI</li>
        <li>Django</li>
        <li>Node.js</li>
        <li>NestJS</li>
        <li>Express</li>
        <li>PostgreSQL</li>
        <li>SQLAlchemy</li>
        <li>Redis</li>
        <li>SQLite</li>
        <li>Prisma ORM</li>
        <li>REST APIs</li>
        <li>AWS Lambda</li>
        <li>AWS ECS</li>
        <li>AWS S3</li>
        <li>AWS SQS</li>
        <li>Docker</li>
        <li>Kubernetes</li>
        <li>RabbitMQ</li>
        <li>OpenTelemetry</li>
        <li>Pytest</li>
        <li>Jest</li>
        <li>Ruff</li>
        <li>CI/CD</li>
        <li>Claude Code</li>
        <li>GitHub Copilot</li>
        <li>Git</li>
        <li>TypeScript</li>
        <li>React</li>
        <li>JavaScript</li>
      </ul>
    </article>
```

---

### Task 4: Adicionar experiência — Esthetic Fast Scheduler

**Files:**
- Modify: `index-backend-pleno.html`

- [ ] **Step 1: Abrir seção de experiência e adicionar Esthetic Fast Scheduler**

```html
    <article itemscope itemtype="https://schema.org/Person">
      <h2 class="pt">EXPERIÊNCIA PROFISSIONAL</h2>
      <h2 class="en" style="display: none">PROFESSIONAL EXPERIENCE</h2>

      <article itemscope itemtype="https://schema.org/WorkExperience">
        <div class="project-header">
          <h3 class="pt">Desenvolvedor Backend Python — Cliente (Esthetic Fast Scheduler)</h3>
          <h3 class="en" style="display: none">Backend Python Developer — Client Project (Esthetic Fast Scheduler)</h3>
          <span class="project-time">(2026)</span>
        </div>
        <ul>
          <li class="pt">
            Desenvolvi backend em <strong>FastAPI</strong> para automação de agendamentos via WhatsApp para studios de estética, com <strong>arquitetura multi-tenant</strong>, integração com Evolution API e fluxo conversacional completo em português.
          </li>
          <li class="pt">
            Modelei banco de dados relacional com <strong>SQLAlchemy 2.0 + PostgreSQL</strong> (tenants, clientes, conversas, serviços, horários de funcionamento, bloqueios, agendamentos e snapshots) e versionei migrações com Alembic.
          </li>
          <li class="pt">
            Implementei <strong>webhook de mensagens WhatsApp</strong> com parser de payloads, deduplicação por mensagem do provedor, resolução de identidade WhatsApp/LID e <strong>máquina de estados persistida</strong> para conduzir o fluxo conversacional.
          </li>
          <li class="pt">
            Criei <strong>motor de disponibilidade de horários</strong> considerando horário comercial, bloqueios manuais, duração total de múltiplos serviços, buffer entre atendimentos e conflitos com agendamentos pendentes ou confirmados.
          </li>
          <li class="pt">
            Apliquei boas práticas: testes automatizados com <strong>Pytest</strong>, linting com <strong>Ruff</strong>, logs estruturados em JSON, rate limiting em memória, migrações versionadas com seed de dados e configuração por variáveis de ambiente.
          </li>

          <li class="en" style="display: none">
            Built a <strong>FastAPI</strong> backend for WhatsApp-based appointment automation for aesthetic studios, with <strong>multi-tenant architecture</strong>, Evolution API integration, and complete conversational flow in Portuguese.
          </li>
          <li class="en" style="display: none">
            Modeled relational database with <strong>SQLAlchemy 2.0 + PostgreSQL</strong> (tenants, clients, conversations, services, business hours, blocks, bookings and service snapshots) versioned with Alembic.
          </li>
          <li class="en" style="display: none">
            Implemented <strong>WhatsApp message webhook</strong> with payload parsing, provider message deduplication, WhatsApp/LID identity resolution, and <strong>persisted state machine</strong> to drive conversational flow.
          </li>
          <li class="en" style="display: none">
            Created <strong>availability engine</strong> considering business hours, manual blocks, total duration of multiple services, buffer between appointments, and conflicts with pending or confirmed bookings.
          </li>
          <li class="en" style="display: none">
            Applied best practices: automated testing with <strong>Pytest</strong>, linting with <strong>Ruff</strong>, structured JSON logs, in-memory rate limiting, versioned migrations with data seeding, and environment-based configuration.
          </li>
        </ul>
      </article>
```

---

### Task 5: Adicionar experiência — ALLM

**Files:**
- Modify: `index-backend-pleno.html`

- [ ] **Step 1: Adicionar experiência ALLM com foco em backend**

```html
      <article itemscope itemtype="https://schema.org/WorkExperience">
        <div class="project-header">
          <h3 class="pt">Desenvolvedor Backend Sênior — ALLM (Plataforma SaaS Médica)</h3>
          <h3 class="en" style="display: none">Senior Backend Developer — ALLM (Medical SaaS Platform)</h3>
          <span class="project-time">(2025 - 2026)</span>
        </div>
        <ul>
          <li class="pt">
            Projetei e implementei o <strong>backend completo de uma plataforma SaaS B2B multi-tenant</strong> em NestJS 11 + TypeScript, com APIs REST para fóruns médicos, casos clínicos com schema dinâmico configurável por comunidade e notificações push multi-plataforma.
          </li>
          <li class="pt">
            Arquitetei sistema de <strong>autorização granular por comunidade</strong> com 5 papéis hierárquicos, RBAC via guards compostos e <strong>audit trail forense</strong> — garantindo isolamento de dados entre tenants e conformidade LGPD.
          </li>
          <li class="pt">
            Implementei <strong>pipeline assíncrono de processamento de mídia</strong> via AWS Lambda com anonimização automática de imagens DICOM (remoção de PHI de pacientes) e status tracking assíncrono via SQS.
          </li>
          <li class="pt">
            Estruturei <strong>CI/CD em GitHub Actions</strong> com Docker multi-stage, migrations isoladas em Fargate, deploy zero-downtime em ECS e injeção dinâmica de secrets do Secrets Manager por ambiente.
          </li>
          <li class="pt">
            Configurei <strong>observabilidade com OpenTelemetry + Winston estruturado</strong> para rastreamento distribuído em produção; escrevi 68 suites de testes com 73K+ LOC de regras de negócio em contextos autenticados.
          </li>

          <li class="en" style="display: none">
            Designed and implemented the <strong>full backend of a B2B multi-tenant medical SaaS platform</strong> with NestJS 11 + TypeScript, REST APIs for medical forums, clinical cases with community-configurable dynamic schemas, and multi-platform push notifications.
          </li>
          <li class="en" style="display: none">
            Architected a <strong>per-community layered authorization system</strong> with 5 hierarchical roles, composed guards RBAC, and <strong>forensic audit logging</strong> — enforcing data isolation between tenants and LGPD compliance.
          </li>
          <li class="en" style="display: none">
            Built <strong>async media processing pipeline</strong> via AWS Lambda with automated DICOM image anonymization (PHI removal) and async status tracking via SQS.
          </li>
          <li class="en" style="display: none">
            Structured <strong>CI/CD in GitHub Actions</strong> with multi-stage Docker builds, isolated Fargate migrations, zero-downtime ECS deployments, and dynamic secret injection per environment via Secrets Manager.
          </li>
          <li class="en" style="display: none">
            Configured <strong>observability with OpenTelemetry + structured Winston logging</strong> for distributed tracing in production; wrote 68 test suites with 73K+ LOC of authenticated business-rule specs.
          </li>
        </ul>
      </article>
```

---

### Task 6: Adicionar experiência — Startamus Pleno

**Files:**
- Modify: `index-backend-pleno.html`

- [ ] **Step 1: Adicionar Startamus Pleno com título e bullets reposicionados para backend**

```html
      <article itemscope itemtype="https://schema.org/WorkExperience">
        <div class="project-header">
          <h3 class="pt">Desenvolvedor Backend Pleno — Startamus</h3>
          <h3 class="en" style="display: none">Mid Backend Developer — Startamus</h3>
          <span class="project-time">(OUT/2022 - 2024)</span>
        </div>
        <ul>
          <li class="pt">
            Gerenciei time de backend no desenvolvimento de <strong>RESTful APIs com Django REST Framework</strong>, estabelecendo padrões de código, coordenando code reviews e garantindo alta performance em aplicações web e mobile.
          </li>
          <li class="pt">
            Arquitetei integrações críticas com <strong>AWS S3</strong>, Twilio (SMS, WhatsApp, email) e <strong>PostgreSQL</strong>, garantindo melhor uptime e segurança dos dados.
          </li>
          <li class="pt">
            Liderei modernização de sistema legado implementando <strong>clean code e design patterns</strong>, resultando em redução de 40% no tempo de carregamento e aumento de 25% na taxa de conversão.
          </li>
          <li class="pt">
            Coordenei equipes multidisciplinares com metodologias ágeis (Scrum/Kanban), práticas de code review e integração contínua.
          </li>

          <li class="en" style="display: none">
            Managed backend team developing <strong>RESTful APIs with Django REST Framework</strong>, establishing coding standards, coordinating code reviews, and ensuring high performance for web and mobile applications.
          </li>
          <li class="en" style="display: none">
            Architected critical integrations with <strong>AWS S3</strong>, Twilio (SMS, WhatsApp, email), and <strong>PostgreSQL</strong>, ensuring better uptime and data security.
          </li>
          <li class="en" style="display: none">
            Led legacy system modernization implementing <strong>clean code and design patterns</strong>, resulting in 40% reduction in load time and 25% increase in conversion rate.
          </li>
          <li class="en" style="display: none">
            Coordinated cross-functional teams using agile methodologies (Scrum/Kanban), code review practices, and continuous integration.
          </li>
        </ul>
      </article>
```

---

### Task 7: Adicionar experiências — Gotech DS e UFPA + fechar seções

**Files:**
- Modify: `index-backend-pleno.html`

- [ ] **Step 1: Adicionar Gotech DS (enxuto, foco em backend)**

```html
      <article itemscope itemtype="https://schema.org/WorkExperience">
        <div class="project-header">
          <h3 class="pt">Desenvolvedor Full-Stack — Gotech DS</h3>
          <h3 class="en" style="display: none">Full-Stack Developer — Gotech DS</h3>
          <span class="project-time">(MAI/2022 - OUT/2022)</span>
        </div>
        <ul>
          <li class="pt">
            Desenvolvi plataforma de e-commerce de rifas com <strong>16.000 usuários cadastrados</strong>, autenticação JWT com múltiplos níveis de acesso, <strong>PostgreSQL</strong> e Docker em ambiente remoto com Git Flow.
          </li>
          <li class="pt">
            Construí dashboard financeiro para gerenciamento de empréstimos de Fintech com <strong>2.000 usuários cadastrados</strong>.
          </li>

          <li class="en" style="display: none">
            Built a raffle e-commerce platform with <strong>16,000 registered users</strong>, JWT authentication with multiple access levels, <strong>PostgreSQL</strong>, and Docker in a remote Git Flow environment.
          </li>
          <li class="en" style="display: none">
            Built financial dashboard for Fintech loan management with <strong>2,000 registered users</strong>.
          </li>
        </ul>
      </article>
```

- [ ] **Step 2: Adicionar UFPA (foco em Python) e fechar todas as sections**

```html
      <article itemscope itemtype="https://schema.org/WorkExperience">
        <div class="project-header">
          <h3 class="pt">Desenvolvedor — UFPA</h3>
          <h3 class="en" style="display: none">Developer — UFPA</h3>
          <span class="project-time">(AGO/2021 - JAN/2022)</span>
        </div>
        <ul>
          <li class="pt">
            Desenvolvi o <strong>LABVCON v2.0</strong> em <strong>Python + Streamlit</strong> para aplicação de controladores avançados (IMC, GPC, GMV) em protótipos reais com Arduino, com monitoramento de dados e métricas de eficiência em tempo real.
          </li>

          <li class="en" style="display: none">
            Built <strong>LABVCON v2.0</strong> in <strong>Python + Streamlit</strong> for applying advanced controllers (IMC, GPC, GMV) on real Arduino prototypes, with real-time data monitoring and efficiency metrics.
          </li>
        </ul>
      </article>

    </article>
```

---

### Task 8: Adicionar educação e fechar body

**Files:**
- Modify: `index-backend-pleno.html`

- [ ] **Step 1: Adicionar seção de educação e fechar o arquivo**

```html
    <section itemscope itemtype="https://schema.org/EducationalOrganization">
      <h2 class="pt">EDUCAÇÃO</h2>
      <h2 class="en" style="display: none">EDUCATION</h2>
      <a class="pt" href="https://cert.efset.org/84VXmr" target="_blank"><strong>Inglês Avançado - C1 </strong></a>
      <a class="en" style="display: none" href="https://cert.efset.org/84VXmr" target="_blank"><strong>Advanced English - C1 </strong></a>
      <p class="pt"><strong>Análise e Desenvolvimento de Sistemas</strong> - GRAN FACULDADE</p>
      <p class="pt"><strong>Engenharia de Controle e Automação</strong> - IFPA Campus Belém</p>
      <p class="en" style="display: none"><strong>Systems Analysis and Development</strong> - GRAN FACULDADE</p>
      <p class="en" style="display: none"><strong>Control and Automation Engineering</strong> - IFPA Campus Belém</p>
    </section>
  </body>
</html>
```

- [ ] **Step 2: Verificar estrutura do arquivo final**

```bash
grep -c "<article" /home/nelio/github/cv-nelio-dias/index-backend-pleno.html
```
Esperado: 8 (1 resumo, 1 tecnologias, 1 experiência-container, 5 experiências internas)

- [ ] **Step 3: Abrir no browser para verificação visual**

```bash
xdg-open /home/nelio/github/cv-nelio-dias/index-backend-pleno.html
```

- [ ] **Step 4: Commit**

```bash
cd /home/nelio/github/cv-nelio-dias
git add index-backend-pleno.html docs/superpowers/
git commit -m "feat: add backend pleno CV targeted at Python backend role

- New index-backend-pleno.html with bilingual PT/EN support
- Summary repositioned as Backend Pleno Python
- Tech stack reordered: Python ecosystem first (FastAPI, Django, SQLAlchemy)
- Added Esthetic Fast Scheduler (FastAPI/PostgreSQL client project, 2026)
- ALLM reframed as Backend Senior (async pipeline, observability, SQS)
- Startamus Pleno reframed as Backend (Django REST, AWS S3, PostgreSQL)
- Removed pure frontend roles (Startamus/Nuuvem, Startamus/P4F)
- Added AI tools: Claude Code, GitHub Copilot

Co-Authored-By: Claude Sonnet 4.6 <noreply@anthropic.com>"
```

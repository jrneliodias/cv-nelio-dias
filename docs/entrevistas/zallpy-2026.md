# Triagem — Zallpy (Desenvolvedor(a) Full Stack Pleno - React/Node)
**Vaga:** Pessoa Desenvolvedora Full Stack Pleno - React/Node - Remoto (BR)
**Código da vaga:** 9733e4
**Data:** Julho/2026
**CV utilizado:** `dev-fullstack-zallpy.html`

---

## 1. Qual é seu nível de experiência com React (hooks, context, performance, testes)?

Uso React há uns 4 anos, em projetos bem diferentes entre si: dashboards em Next.js, o checkout white-label da P4F/Mapfre e, mais recentemente, o Portal Billing, um SPA em React 19 com TypeScript e Vite que já passou dos 250 componentes e tem uns 60 hooks customizados organizados por domínio. É onde eu passo a maior parte do tempo no dia a dia: useState, useEffect e os hooks customizados que a gente vai extraindo conforme a lógica se repete entre telas.

Pra estado, prefiro Zustand a Context puro, principalmente porque em telas com bastante interação o Context acaba re-renderizando mais coisa do que eu gostaria. Uso TanStack Query pra cache e sincronização com API, e React Hook Form com Zod pra formulário.

Performance também já apareceu na prática: participei da modernização de um checkout legado e chegamos a uns 40% de redução no tempo de carregamento. Em testes, uso Vitest pra unitário; Playwright pra E2E eu apliquei mais em um projeto com SvelteKit do que num React especificamente. Não tenho tanta bagagem com React Testing Library isolado, mas testar componente e fluxo crítico faz parte da rotina.

---

## 2. Qual é seu nível de experiência com Node.js, Express, NestJS?

Meu uso de Node.js é praticamente todo via NestJS. Desde 2022 mantenho o back-end de um SaaS médico, o projeto ALLM, em NestJS 11 com TypeScript. Por baixo o Nest roda sobre Express, então tenho contato direto com essa camada de middlewares, mas nunca cheguei a montar uma API em Express puro do zero. Meu forte mesmo é a estrutura do Nest: módulos, guards compostos, interceptors, RBAC granular por comunidade, papéis hierárquicos, isolamento entre tenants e trilhas de auditoria pra operação sensível.

Nesse projeto modelei os dados com Prisma sobre PostgreSQL e usei Redis pra cache de resultado de query e de token. Também montei um pipeline com AWS Lambda pra processamento assíncrono, anonimizando imagem médica. Autenticação é via Cognito, OAuth2 e JWT, integrado no front e no back. Deploy roda em Docker, GitHub Actions, ECS/Fargate e Secrets Manager, com ambientes separados e migration segura. Jest cobre as regras de negócio mais críticas.

Fora do Node, tenho vivência de back-end em Python também, com Django REST Framework e FastAPI.

---

## 3. Qual é seu nível de experiência com JavaScript e TypeScript?

JavaScript eu uso desde o começo da carreira, em 2021/2022. TypeScript entrou depois e virou padrão em praticamente todo projeto que peguei a partir de 2022. No back-end o NestJS já nasce TypeScript-first, então tipo módulo, DTO e guard o tempo todo. No front uso TypeScript tanto em React (Portal Billing, o checkout da P4F) quanto no SvelteKit, no projeto da Nuuvem.

Gosto de tipar bem a borda das coisas. Uso Zod pra validar formulário e schema de API ao mesmo tempo que ele infere o tipo, e o Prisma já entrega tipagem direto do schema do banco. Meu nível é sólido no TypeScript do dia a dia, o que evita passar undefined onde não devia. Tipo condicional e generics mais elaborados eu não domino, simplesmente porque não apareceram nos projetos que fiz até agora.

---

## 4. Qual é seu nível de experiência com consumo/configuração de APIs REST e GraphQL?

REST é o que uso o tempo todo. Nos últimos anos passei por praticamente todas as pontas dele. No front, consumo com Axios e TanStack Query, cuidando de cache, paginação, filtro por query string e invalidação depois de mutation, isso no Portal Billing e em dashboards administrativos. No back, já projetei endpoint REST em NestJS, em Django REST Framework e em FastAPI. Também montei um módulo de webhooks completo no Portal Billing, com CRUD, ping, reenvio e histórico de request e response, e integrei webhook da Evolution API num projeto de agendamento via WhatsApp.

GraphQL eu não tenho experiência prática nenhuma. Nunca configurei nem consumi uma API GraphQL num projeto real. Entendo a ideia geral por trás dele, mas não vou fingir que já mexi na prática nisso.

---

## 5. Qual é o seu nível de experiência com banco de dados relacionais (PostgreSQL, MySQL) e NoSQL (MongoDB, DynamoDB)?

PostgreSQL é meu banco de dados principal há uns 4 anos. Uso com Prisma no back de Node/NestJS, com SQLAlchemy e Alembic num projeto em FastAPI, e também via Django ORM num outro projeto. É onde tenho modelagem relacional, migration e consulta mais rodada. MySQL eu nunca usei em projeto nenhum.

Do lado NoSQL, o que uso de verdade é Redis, como cache de resultado de query e de token de sessão, tirando carga do banco principal. MongoDB e DynamoDB ficam de fora: não tenho experiência prática com nenhum dos dois, nunca modelei nem integrei em produção.

---

## 6. Qual é o seu nível de experiência com versionamento em Git e GitFlow?

Git eu uso todo dia há uns 4 anos, faz parte do trabalho normal: branch, commit, PR, code review. Git Flow especificamente apliquei na Gotech DS, em 2022, numa plataforma de rifas online que rodava com Scrum. Depois disso, nos projetos que peguei, o fluxo virou branch mais PR revisado antes de mergear, com pipeline de CI/CD (GitHub Actions, GitLab CI, Jenkins). Não chamo isso de Git Flow formalmente, mas a lógica de isolar o trabalho e revisar antes de integrar é a mesma.

---

## 7. Qual é o seu nível de conhecimento em arquiteturas Hexagonal, Microsserviços, Serverless, Micro Front-end e BFF?

Dessas cinco, a única que eu realmente já usei na prática é serverless. No projeto ALLM montei um pipeline com AWS Lambda para processamento assíncrono, anonimizando imagem médica, então tenho experiência real com function rodando sob demanda, sem servidor fixo para manter.

De microsserviços tenho uma vivência parcial. No mesmo projeto, a API principal em NestJS conversa com um serviço de chat separado e com uma estrutura de RAG, cada um com deploy próprio, passando token de autenticação entre eles via chamada de API. Isso é sistema distribuído na prática, mas eu não projetei uma arquitetura de microsserviços do zero, nem mexi com service mesh, fila de mensagem ou service discovery. Contato eu tenho, experiência consolidada eu não diria que tenho.

Hexagonal eu não apliquei em nenhum projeto. Micro Front-end também não, tenho é experiência construindo aplicações frontend separadas para produtos diferentes (SvelteKit para um cliente, React para outro), o que é uma coisa distinta de compor frontends independentes numa mesma tela. BFF eu também não usei na prática. Dos três, entendo o conceito, mas seria aprendizado, não experiência que eu já tenha.

---

## 8. Qual é o seu nível de conhecimento em segurança (OAuth2, JWT, LGPD/GDPR)?

JWT eu uso em praticamente todo projeto dos últimos 4 anos, é o mecanismo de autenticação padrão em quase tudo que fiz: Nuuvem, Gotech DS, Portal Billing, ALLM. OAuth2 apliquei via AWS Cognito no projeto ALLM, integrando login descentralizado no front e no back.

Em segurança de um modo mais amplo, no ALLM trabalhei com RBAC granular, guards compostos, papéis hierárquicos, isolamento entre tenants, trilha de auditoria para operação sensível e gestão de secret com AWS Secrets Manager. Esse projeto lida com dado de paciente, incluindo um pipeline de anonimização de imagem médica.

LGPD e GDPR eu não tenho experiência formal. Nunca participei de um processo de adequação ou auditoria ligado a nenhuma das duas leis. A anonimização de imagem vai na direção de proteção de dado pessoal, mas é diferente de ter trabalhado com compliance de LGPD ou GDPR.

---

## 9. Qual é o seu nível de conhecimento em AWS e serviços Cloud?

AWS eu uso na prática desde 2022, principalmente no projeto ALLM. Uso Lambda para um pipeline de processamento assíncrono que anonimiza imagem médica, e ECS/Fargate para rodar o backend em container, junto com Docker, GitHub Actions e Prisma, com ambientes separados e migration segura. Secrets Manager cuida da gestão de secret e variável de ambiente sensível, e o Cognito é o provedor de autenticação, OAuth2 e JWT, integrado no front e no back.

Também integrei uma estrutura de RAG construída sobre o Bedrock, usando o Claude da Anthropic como modelo para consultar documentação técnica e responder pergunta de usuário. E usei S3 para armazenamento de arquivo num outro projeto, esse com Django REST Framework e integração com Twilio.

Fora desses serviços eu não tenho experiência com AWS. Infraestrutura como código, Terraform, CloudFormation, ainda não usei nada disso.

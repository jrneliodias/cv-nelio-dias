# Memória de entrevistas

Base de consulta para responder triagens e entrevistas com consistência. Antes de escrever respostas novas, consultar este arquivo e as entrevistas anteriores. Depois, atualizar o índice e o banco de histórias.

---

## Índice de entrevistas

| Arquivo | Empresa / vaga | Data | Tipo de perguntas | CV usado |
|---|---|---|---|---|
| [luby-2026.md](luby-2026.md) | Luby, Fullstack Node/React Pleno | Jun/2026 | Técnicas: stack, case, microsserviços, qualidade, cloud, CI/CD, IA | `dev-fullstack-luby.html` |
| [zallpy-2026.md](zallpy-2026.md) | Zallpy, Full Stack Pleno React/Node | Jul/2026 | Nível por tecnologia: React, Node, TS, REST/GraphQL, bancos, Git, arquiteturas, segurança, AWS | `dev-fullstack-zallpy.html` |
| [fullstack-comportamental-2026.md](fullstack-comportamental-2026.md) | Fullstack (empresa não informada) | Out/2026 | Comportamentais: ponta a ponta, fluxo de trabalho, prioridades, bloqueios, conflitos, colaboração | `dev-fullstack.html` |

---

## Números e fatos que se repetem

Usar sempre os mesmos números, sem arredondar para cima.

- **Experiência:** 4+ anos. Profissional desde mai/2022 (Gotech DS); antes disso, UFPA desde ago/2021.
- **Startamus:** out/2022 até hoje. Startup B2B que atende clientes de SaaS médico, fintech e gaming.
- **Checkout P4F / MAPFRE Pay:** parceria de 2 anos, cerca de 40% de redução no tempo de carregamento do checkout legado, pagamento por cartão, Pix, boleto e débito direto.
- **Portal Billing:** 35 páginas, 259 componentes e 61 hooks. React 19, TS e Vite. Deploy via Jenkins e Firebase Hosting, monitoramento com Sentry.
- **White-label:** permitiu a entrada de MAPFRE, Sura e HDI na plataforma.
- **Gotech DS:** e-commerce de rifas com cerca de 16.000 usuários cadastrados e integração com Mercado Pago.
- **Formação:** ADS (GRAN), Eng. de Controle e Automação (IFPA), inglês C1 (EF SET).

---

## Banco de histórias (STAR)

Cada história lista as perguntas em que já foi usada. **Status** indica se a história já foi confirmada pelo Nélio ou ainda é uma narrativa montada a partir do CV que ele precisa validar.

### H1. Portal Billing de ponta a ponta
- **Situação:** a P4F precisava de uma plataforma financeira B2B para cobrança, inadimplência, comissões e recebíveis.
- **Ação:** levantamento com o time financeiro, arquitetura por domínio, RBAC, white-label, webhooks, exportação assíncrona, i18n, CI/CD e Sentry.
- **Resultado:** 35 páginas e mais de 250 componentes; viabilizou a entrada de novas corretoras.
- **Serve para:** projeto de ponta a ponta, arquitetura, case de sucesso, autonomia.
- **Usada em:** Luby #2, Comportamental #1.
- **Status:** fatos confirmados (CV).

### H2. Checkout white-label P4F / MAPFRE Pay
- **Situação:** checkout legado lento e difícil de manter.
- **Ação:** modernização em React e fluxos white-label com 4 meios de pagamento, em conjunto com Backend, QA e Produto.
- **Resultado:** cerca de 40% menos tempo de carregamento; consolidou a parceria e abriu espaço para o Portal Billing.
- **Serve para:** performance, case de sucesso, impacto no negócio.
- **Usada em:** Luby #2, Zallpy #1.
- **Status:** fatos confirmados (CV).

### H3. Automação de relatórios médicos com Claude (ALLM)
- **Situação:** médicos faziam à mão a primeira leitura dos exames.
- **Ação:** exames convertidos em JSON e processados por prompts estruturados para gerar uma triagem inicial; prompts ajustados com quem conhecia o domínio.
- **Resultado:** tirou um processo manual do papel e agilizou o atendimento.
- **Serve para:** reconhecimento, iniciativa, IA, foco no usuário.
- **Usada em:** Luby #7, Comportamental #5.
- **Status:** fatos confirmados (CV). **Quem reconheceu a contribuição ainda não foi validado.**

### H4. Colaboração com o time financeiro (não técnico)
- **Ação:** pedir para o time mostrar como fazia o processo no dia a dia, evitar jargão, validar com telas em homologação e registrar as decisões.
- **Resultado:** daí saíram o upload de CSV, os relatórios agendados e os filtros.
- **Serve para:** colaboração com outras áreas, levantamento de requisitos.
- **Usada em:** Comportamental #6.
- **Status:** narrativa montada a partir do CV. **Validar.**

### H5. Discordância sobre a exportação síncrona
- **Ação:** levar dados de volume, propor exportação assíncrona e respeitar que a decisão final era de Produto.
- **Resultado:** a exportação assíncrona foi adotada e reaproveitada no agendamento de relatórios.
- **Serve para:** discordância com Produto ou negócio, argumentação técnica.
- **Usada em:** Comportamental #7.
- **Status:** narrativa montada. **Validar se a discordância aconteceu de fato.**

### H6. Divergência sobre Context API e Zustand/TanStack Query
- **Ação:** levar a discussão do PR para uma chamada, mostrar um exemplo de re-render e ouvir o argumento do colega contra adicionar dependência.
- **Resultado:** Context para estado global estável, Zustand e TanStack Query para o resto, com o critério documentado.
- **Serve para:** conflito com colega, code review.
- **Usada em:** Comportamental #9.
- **Status:** narrativa montada a partir da preferência técnica real (Zallpy #1). **Validar.**

### Outras histórias disponíveis (ainda não usadas)
- **Pipeline Lambda de anonimização de imagens médicas (ALLM):** serverless, segurança, dados sensíveis.
- **RBAC granular, isolamento entre tenants e auditoria (ALLM):** segurança, multi-tenant.
- **Redis para cache de queries e tokens (ALLM):** performance de backend.
- **Nuuvem em SvelteKit:** gamepad, i18n em 5 idiomas, GitLab CI com Vitest e Playwright.
- **Esthetic Fast Scheduler:** projeto pessoal feito sozinho de ponta a ponta, com FastAPI, LangChain multi-provider, WhatsApp e motor de disponibilidade.
- **Claude Code com TDD:** acelerou entregas e geração de testes.

---

## Limites honestos

Já declarados em entrevistas. Manter a mesma resposta para não haver contradição.

- **Sem experiência prática:** GraphQL, MySQL, MongoDB, DynamoDB, arquitetura hexagonal, micro front-end, BFF, Terraform/CloudFormation (IaC) e compliance de LGPD/GDPR.
- **Experiência parcial:** microsserviços (serviços separados com tokens entre eles, mas sem projetar do zero, sem filas e sem service mesh), Express puro (só por baixo do Nest), React Testing Library isolado, TypeScript avançado (tipos condicionais e generics complexos).
- **Git Flow formal:** apenas na Gotech DS. Depois, fluxo de branch e PR revisado.

---

## Estilo das respostas

- Primeira pessoa e tom natural, como em uma conversa. A Zallpy é a referência de tom.
- Começar pela situação real, com projeto e número concreto, e só depois falar de princípios.
- Admitir lacunas com clareza, citando o que existe de mais próximo, sem inflar.
- Nas perguntas comportamentais, usar estrutura STAR e terminar com o resultado.
- Antes de enviar, sinalizar ao Nélio as histórias que são narrativa montada, para ele validar.

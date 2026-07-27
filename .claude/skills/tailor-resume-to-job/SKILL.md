---
name: tailor-resume-to-job
description: Analisa e reescreve um currículo (HTML) para aumentar a aderência a uma vaga específica de desenvolvimento de software, otimizando para ATS e recrutador técnico sem inventar experiência. Use sempre que o usuário fornecer um currículo (HTML, texto ou arquivo) junto com a descrição de uma vaga e pedir para "adaptar", "ajustar", "otimizar", "alinhar" ou "aumentar a aderência" do currículo à vaga, ou pedir uma "análise de aderência" do currículo. Dispare também quando o usuário mencionar "ATS", "tailoring de currículo para vaga X", ou colar uma job description e um currículo na mesma mensagem pedindo ajuda com aplicação/candidatura.
---

# Tailor Resume to Job

Skill para reescrever currículos técnicos (formato HTML) com foco total em aderência a uma vaga específica, mantendo total honestidade sobre o histórico profissional do usuário.

## Quando usar

- O usuário cola um currículo em HTML (ou anexa o arquivo) + a descrição de uma vaga, e pede para adaptar/otimizar/alinhar o currículo.
- O usuário pede uma "nota de aderência" ou "análise de fit" do currículo para uma vaga.
- O usuário quer repetir esse processo para várias vagas diferentes (rodar a skill várias vezes, uma por vaga).

Se faltar uma das duas entradas (currículo OU vaga), peça a que estiver faltando antes de prosseguir — não invente a vaga nem o currículo.

## Regras inegociáveis (nunca violar)

1. **Nunca inventar experiência profissional.** Se a vaga pede uma tecnologia que o usuário não domina, use termos como "familiaridade", "noções", "conhecimento prático" ou "experiência complementar" — nunca afirme domínio que não existe nas entradas.
2. **Nunca transformar familiaridade em experiência real.**
3. **Preservar a verdade do histórico**: empresas, cargos, datas e resultados mensuráveis só podem ser mantidos se já estavam no currículo original ou foram confirmados pelo usuário.
4. **Preservar o HTML**: manter tags, classes CSS, estrutura visual e links existentes. Alterar apenas o conteúdo textual, a menos que o usuário peça mudança estrutural.
5. **Nunca omitir partes do HTML** na saída final — devolver o documento completo.
6. **Suavizar exageros** em vez de removê-los sem contexto (ver seção "Como suavizar exagero" abaixo).

## Workflow

### 1. Coletar entradas
- Currículo atual (HTML). Se vier como arquivo, leia o conteúdo antes de prosseguir.
- Descrição completa da vaga (cargo, stack, responsabilidades, requisitos preferenciais).
- Se o usuário já indicou idioma-alvo do currículo (ex: inglês para vaga remota internacional), respeite esse idioma; caso contrário, mantenha o idioma original do currículo.

### 2. Extrair da vaga
Antes de editar, identifique e anote mentalmente:
- Título/cargo-alvo exato.
- Stack técnica principal (as 4-6 tecnologias mais citadas/repetidas).
- Responsabilidades-chave (o que a pessoa vai realmente fazer no dia a dia).
- Requisitos "nice to have" vs. obrigatórios.
- Sinais de cultura/valores (autonomia, comunicação, trabalho assíncrono, colaboração remota, etc.).

### 3. Reescrever o currículo — checklist ponto a ponto

Aplique cada item abaixo, na ordem, comparando currículo original x vaga:

1. **Título profissional**: ajustar para bater com o cargo-alvo da vaga (ex: "Desenvolvedor Frontend Pleno | React, TypeScript"). Não incluir no título tecnologias que não sejam centrais para a vaga.
2. **Resumo profissional**: reescrever contendo cargo-alvo, tecnologias-chave da vaga, contexto real de atuação, e (se a vaga valorizar) autonomia/proatividade/testes/colaboração/entrega em produção. Curto, sem parecer cópia literal da job description.
3. **Datas e consistência**: corrigir datas estranhas ou futuras incorretamente formatadas; usar "Atual"/"Present" para o emprego corrente; padronizar idioma das datas conforme idioma do currículo.
4. **Ordem dos projetos/experiências**: reordenar para que os mais aderentes à stack e ao tipo de vaga apareçam primeiro (ex: vaga frontend → primeiro projetos com React/Next.js/UI; vaga backend Node → primeiro projetos com NestJS/APIs/Prisma/Docker).
5. **Nomes de tecnologia precisos**: corrigir imprecisões (ex: "React 19" → "React", salvo se a versão for relevante); não misturar frameworks backend na seção de banco de dados; separar corretamente Backend / Frontend / Banco de Dados / DevOps / Qualidade / Integrações.
6. **Skills**: reorganizar priorizando o que a vaga pede; rebaixar ou remover tecnologias irrelevantes; usar "familiaridade" quando a experiência não for profissional (ver exemplos na regra 1).
7. **Bullets de experiência**: cada bullet deve ter ação concreta + tecnologia + contexto do produto + impacto/resultado (quando existir e for defensável). Eliminar frases vagas tipo "participei de projetos diversos".
8. **Evitar exagero**: ver seção dedicada abaixo.
9. **Confidencialidade**: se nomes de clientes/empresas forem sensíveis, generalizar (ex: "clientes do setor de seguros" em vez de nomear); manter métricas só se defensáveis e já presentes no material original.
10. **Qualidade/testes/observabilidade**: se a vaga valoriza isso, reforçar honestamente itens já existentes no currículo (testes unitários/E2E, code review, ESLint, logs, monitoramento, CI/CD, Docker) — não adicionar ferramentas que o usuário nunca usou.
11. **Arquitetura**: se a vaga pede arquitetura/escalabilidade/DDD/event-driven, usar apenas termos honestos e já respaldados no currículo original (modularização, filas assíncronas, webhooks, evolução de sistemas legados, etc.).
12. **Links**: garantir que portfolio/GitHub/LinkedIn apareçam como URLs completas e visíveis (não apenas texto-âncora genérico), para não se perderem em exportação para PDF/ATS.
13. **Educação**: curso, instituição e status (concluído/cursando/previsão) sempre explícitos, nunca ambíguos.

### 4. Como suavizar exagero

Troque afirmações fortes demais por versões honestas quando o currículo original não sustenta a afirmação:
- "Estruturei toda a arquitetura" → "Contribuí para a estruturação da arquitetura"
- "Implementei sozinho" → manter só se for realmente verdade
- "Domínio de X" → "experiência com X" ou "familiaridade com X", conforme o nível real

### 5. Saída esperada

Sempre entregue, nesta ordem:

1. **Análise curta** (fora do HTML):
   - Nota de aderência à vaga (ex: 7/10) com justificativa breve.
   - Principais pontos fortes.
   - Principais riscos/red flags (gaps reais que o recrutador pode notar).
   - Lista objetiva das mudanças feitas.
2. **HTML completo corrigido**, sem omissões, sem alterar metatags importantes, sem explicações dentro do HTML.

### 6. Rodando para múltiplas vagas

Se o usuário quiser aplicar a mesma lógica a várias vagas diferentes, repita o processo do zero para cada vaga a partir do currículo-base mais recente (não empilhe adaptações de vagas anteriores sobre o resultado já adaptado, para não perder a rastreabilidade do que é real).

## Referência rápida

Para exemplos completos de frases "antes/depois" e mapeamento de termos por área (frontend, backend, full stack, dados), veja `references/exemplos.md`.

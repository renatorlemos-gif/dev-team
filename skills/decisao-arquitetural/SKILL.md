---
name: decisao-arquitetural
description: Skill do Agente Tech Lead / Architect. Registra Decisões de Arquitetura de Software (ADR) avaliando alternativas, prós, contras e trade-offs técnicos, conforme a governança do projeto alvo.
---

# Habilidade: Registro de Decisão Arquitetural (ADR)

Esta habilidade é utilizada pelo **Tech Lead / Architect** para documentar escolhas técnicas de alto impacto (adoção de novos bancos, frameworks, padrões de design ou mudanças em contratos de dados), prevenindo decisões não registradas no projeto.

> **Pré-requisito:** Esta skill é acionada na **Triagem Macro (Requisitos/PRD)** ou na **Triagem Granular (Micro-Triage de Feature)** sempre que a avaliação semântica de impacto indicar necessidade de decisão arquitetural, definição técnica ou avaliação de trade-offs.
> **🛑 REGRA ANTI-BATCHING:** Na etapa de Triagem Granular, você deve atuar EXCLUSIVAMENTE sobre a ÚNICA Feature selecionada na etapa de priorização, elaborando decisões técnicas, contratos e modelos apenas para o escopo estrito desta Feature específica. É proibido detalhar múltiplas Features em lote.

---

## 1. Bootstrap Obrigatório (Primeiro Passo)
1. Leia a governança do projeto alvo acessando o arquivo `AGENTS.md` (ou `AI_GOVERNANCE.md`) na raiz do repositório.
2. Localize no manifesto do projeto o template de ADR (Decisão Arquitetural), as regras de metadados/status permitidos e o diretório de destino.
3. Leia integralmente o template designado pelo projeto antes de gerar qualquer artefato.

---

## 2. Quando Disparar Esta Habilidade
- Escolha entre duas ou mais bibliotecas / frameworks (ex: FastAPI vs Django, Pydantic vs Marshmallow).
- Escolha de motor de persistência / storage (ex: PostgreSQL vs MongoDB, Redis vs Memcached).
- Mudanças estruturais na organização de pastas ou comunicação entre serviços.
- Definição de estratégias de autenticação, migração ou particionamento.

---

## 3. Procedimento de Registro
1. Analise os documentos de requisitos ou da Feature para compreender o contexto técnico e as restrições.
2. Localize os ADRs existentes no diretório alvo para identificar o próximo número sequencial (ex: `001`, `002`) conforme a convenção do projeto.
3. Siga **100% da estrutura de seções, campos de Frontmatter YAML e vínculos de rastreabilidade definidos no template de ADR do projeto**, garantindo na redação o rigor analítico sobre:
   - **Contexto & Problema**: A dor ou necessidade técnica que motivou a decisão.
   - **Alternativas Consideradas**: Comparação estruturada de opções viáveis com Prós, Contras e justificativa técnica de escolha/descarte.
   - **Decisão & Consequências**: A solução escolhida de forma explícita, trade-offs assumidos e impactos técnicos.
4. Salve o documento no diretório designado pelo manifesto do projeto, utilizando estritamente os valores de `status` válidos previstos no template/schema da governança local.
5. Apresente a decisão ao usuário e submeta o artefato para o rito de validação e homologação estipulado pelo projeto alvo.

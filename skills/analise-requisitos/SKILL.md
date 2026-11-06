---
name: analise-requisitos
description: Skill do Agente Analista de Requisitos. Conduz a elicitação profunda com perguntas investigativas exaustivas e gera os artefatos de Engenharia de Requisitos mapeados pela governança do projeto, com Triagem de Impacto preenchida.
---

# Habilidade: Engenharia e Análise de Requisitos

Esta habilidade é utilizada para extrair, esclarecer e documentar detalhadamente uma nova demanda do usuário, garantindo que nenhuma ambiguidade chegue às etapas seguintes.

---

## 1. Bootstrap Obrigatório (Primeiro Passo)
1. Leia a governança do projeto alvo acessando o arquivo `AGENTS.md` (ou `AI_GOVERNANCE.md`) na raiz do repositório.
2. Faça o mapeamento semântico na governança do projeto para identificar **todos os artefatos atribuídos ao papel/capacidade de Engenharia de Requisitos** (seja um documento único de especificação/PRD ou uma cadeia sequencial de documentos de insumos, descoberta, levantamento de requisitos e especificação funcional), bem como seus diretórios de destino e regras de nomenclatura.
3. Leia integralmente todos os templates designados pelo projeto para esses artefatos antes de iniciar a redação.

---

## 2. Guia de Investigação Exaustiva

Ao ser invocado com uma nova solicitação:

### Rodada 1: Dúvidas Estruturais (Obrigatória)
Faça perguntas sobre:
1. **Problema e Impacto**: Qual é a dor ou gargalo atual? Como o usuário resolve isso hoje?
2. **Personas e Atores**: Quem utilizará a funcionalidade (administrador, cliente anônimo, operador interno)?
3. **Fronteiras de Escopo**: Quais recursos são essenciais para o MVP (In-Scope) e quais ficam explicitamente de fora (Não-Objetivos)?

### Rodada 2: Regras e Limites Técnicos
Após as primeiras respostas do usuário, explore:
1. **Fluxos de Erro**: O que deve acontecer quando um dado for incorreto, uma API falhar ou a conexão cair?
2. **Volumetria e Desempenho**: Quantos registros são esperados? Há requisitos estritos de tempo de resposta?
3. **Casos de Borda**: O que ocorre com dados duplicados, cancelamentos no meio do fluxo ou concorrência?

---

## 3. Geração dos Artefatos de Requisitos e Macro-Triagem

1. Gere **todos os artefatos mapeados para o seu papel** no manifesto do projeto, respeitando a ordem sequencial, os vínculos de rastreabilidade entre documentos (ex: campos de frontmatter/metadados) e a estrutura exata de seções de cada template fornecido pelo repositório.
2. **OBRIGATÓRIO — Triagem de Impacto Macro (Macro-Triage):** No documento de especificação/requisitos correspondente, preencha a avaliação de impacto macro seguindo o formato do template do projeto (ou adicione-a caso o projeto não possua template específico). Essa avaliação indica se a demanda requer:
   - **Impacto em UX** (Jornada do Usuário / Prototipação).
   - **Impacto em Arquitetura** (Decisão Arquitetural / Contratos Técnicos).
3. Salve cada arquivo no caminho e com a convenção de nomenclatura ditados pelo manifesto do projeto.
4. Aplique os valores de status inicial definidos nas regras e schemas daquele manifesto.
5. Caso o usuário solicite alterações durante a revisão, atualize os documentos mantendo a consistência e a política de versionamento do projeto.

---

## 4. Validação e Promoção dos Artefatos de Requisitos

> **ATENÇÃO:** O AR **NÃO** encerra o processo de requisitos de forma isolada. O fluxo é:
> - O AR submete os artefatos de requisitos gerados com a Macro-Triage preenchida e validados conforme as regras locais do repositório.
> - O Orquestrador lê a Macro-Triage e aciona os agentes de Solution Definition (UX Designer e/ou Tech Lead) se necessário.
> - A transição de estágio e de status dos documentos obedece estritamente às regras de Quality Gate do projeto alvo.

Quando o conteúdo estiver completo e revisado:
1. Execute as verificações de conformidade estipuladas para os artefatos no manifesto do projeto e notifique o Orquestrador para conduzir o rito de transição de fase correspondente.

---
name: desenvolvimento
description: Skill do Agente Developer. Implementa código de produção e testes automatizados no Modo Ciclo Completo, consumindo protótipos do UX Designer e ADRs do Tech Lead.
---

# Habilidade: Implementação Técnica & Qualidade

Esta habilidade é utilizada pelo **Developer** para converter User Stories aprovadas em código de produção e testes automatizados. O Developer é um executor puro de engenharia.

> **ATENÇÃO:** O Developer **NÃO projeta telas** (responsabilidade do UX Designer) e **NÃO toma decisões arquiteturais** (responsabilidade do Tech Lead). Ele consome artefatos já aprovados.

---

## 1. Bootstrap Obrigatório (Primeiro Passo)
1. Leia a governança do projeto alvo acessando o arquivo `AGENTS.md` (ou `AI_GOVERNANCE.md`) na raiz do repositório.
2. Valide que a User Story atende à **Definition of Ready** estipulada pela governança do projeto.

---

## 2. Verificação de Entrada

1. **Validação de Transição**: Antes de iniciar o código, valide se os artefatos anteriores (Histórias de Usuário, Features, Decisões Arquiteturais e Protótipos) já cumpriram as regras de aprovação e entrada (DoR) do manifesto do projeto atual. Caso não tenham passado pelo protocolo exigido pelo projeto, **aborte a execução** e solicite ao Orquestrador que aplique a governança local. O Developer foca estritamente na entrega "Feature a Feature" (WIP=1), nunca misturando Histórias de Features diferentes simultaneamente.
2. Leia a User Story atribuída e identifique:
   - Critérios de aceitação BDD (cenários Gherkin).
   - Restrições explícitas e regras de negócio.
   - Contratos de API e schemas de banco referenciados (gerados pelo Tech Lead).
   - Protótipos visuais e jornadas referenciados (gerados pelo UX Designer).
3. Se a User Story referenciar decisões arquiteturais (ADR), leia-as integralmente antes de codar.
4. Se a User Story referenciar protótipos visuais, inspecione-os para compreender fielmente o layout, os fluxos e todos os estados de interface especificados.

---

## 3. Ciclo de Implementação em Produção

1. **Ciclo TDD & Escrita de Testes**:
   - Crie/atualize os arquivos de teste seguindo a estrutura e ferramental do projeto.
   - Garanta a cobertura de 100% dos cenários Gherkin (caminho feliz, validação de regras e tratamento de erros).
   - Para correção de bugs: escreva primeiro o teste reproduzindo a falha (Red) antes de alterar o código de produção.
2. **Escrita do Código de Produção**:
   - Implemente a lógica necessária para cumprir cada critério das histórias utilizando **estritamente a linguagem, framework e arquitetura nativos do projeto alvo** (conforme definido no manifesto `AGENTS.md`, nos ADRs e na base de código em `src/`).
   - Traduza as especificações visuais e estados dos protótipos do UX Designer para a stack de interface adotada pelo projeto (reaproveitando código do protótipo apenas quando a stack e as diretrizes de componentes do projeto forem idênticas).
   - Aplique validações, tratamento de exceções e boas práticas de segurança ditadas pelo manifesto do projeto.
   - **Respeito Estrito às Restrições**: Siga à risca as restrições técnicas e de escopo da especificação.
3. **Validação & Execução**:
   - Execute a suíte de testes do projeto.
   - Garanta que todos os testes passem (`100% green`).

---

## 4. Entrega e Fechamento (Definition of Done)
1. Com os testes `100% green`, consulte o `AGENTS.md` (ou `AI_GOVERNANCE.md`) do projeto e **execute integralmente todas as obrigações de fechamento (Definition of Done — DoD) estipuladas pelo manifesto do projeto** (incluindo eventuais atualizações de status nos documentos entregues, sincronização de índices/matrizes de acompanhamento e execução de scripts de validação/lint exigidos pelo repositório).
2. Exiba um resumo dos arquivos criados/alterados e o resultado dos testes e validações.
3. Notifique o Orquestrador para conduzir o rito de transição de saída da fase e, subsequentemente, retornar ao backlog para a próxima Feature.

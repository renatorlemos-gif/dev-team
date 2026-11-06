---
name: refinamento-po
description: Skill do Agente Product Owner. Transforma os artefatos de Requisitos aprovados + Solution Definition em definições de Features, mantém o controle de Backlog do projeto e desdobra Histórias de Usuário ágeis com critérios BDD/Gherkin.
---

# Habilidade: Gestão de Backlog, Features e Refinamento de Histórias BDD

Esta habilidade é utilizada pelo **Product Owner** para decompor a especificação funcional em incrementos entregáveis de valor (Features e Histórias de Usuário), mantendo o backlog estruturado e blindando o time de desenvolvimento contra ambiguidades.

---

## 1. Bootstrap Obrigatório (Primeiro Passo)
1. Leia a governança do projeto alvo acessando o arquivo `AGENTS.md` (ou `AI_GOVERNANCE.md`) na raiz do repositório.
2. Identifique no manifesto do projeto **todos os artefatos, templates e matrizes/índices de acompanhamento mapeados para o papel de Product Owner / Gestão de Produto** (como definições de Funcionalidades/Features, artefatos de controle de Backlog e Histórias de Usuário), bem como seus diretórios de destino.
3. Leia integralmente os templates designados pelo projeto antes de iniciar a redação.

---

## 2. Verificação de Entrada
1. Localize a documentação de requisitos da demanda e verifique se ela cumpriu o estágio de aprovação exigido pelo manifesto do projeto (ex: `Approved`). Caso contrário, **interrompa e solicite que o Orquestrador conclua a fase anterior primeiro**.
2. **Leitura Obrigatória de Artefatos de Solution Definition:** Os artefatos de requisitos aprovados E os artefatos macro gerados na etapa de Solution Definition são insumos obrigatórios. O PO deve consumi-los antes de definir as Features:
   - **Decisões Arquiteturais e Contratos** gerados pelo Tech Lead (se a Triagem indicou impacto em Arquitetura) — para incorporar restrições técnicas e contratos de API/dados.
   - **Protótipos e Jornada UX** gerados pelo UX Designer (se a Triagem indicou impacto em UX) — para referenciar telas, estados e fluxos nas histórias.

---

## 3. Elaboração de Features, Backlog e Histórias de Usuário (Cadência com STOPS)

O Product Owner NÃO deve ir direto para a criação de Histórias de Usuário nem atuar em lote sobre múltiplas Features. Ele deve:
1. **Consumir** a especificação de requisitos aprovada e os artefatos macro (Solution Definition).
2. **Definir as Funcionalidades (Features) e Atualizar o Backlog**: Decomponha o escopo macro em Features, gere os arquivos físicos de definição de Feature e crie/atualize a matriz ou índice de controle de Backlog exatamente conforme mapeado no manifesto do projeto (`AGENTS.md`), apresentando o escopo ao usuário para priorização.
   * **Avaliação de Impacto (Micro-Triagem):** Em cada Feature definida, preencha a seção de triagem granular (conforme o template de Feature do projeto) indicando se há necessidade de refinamento visual/UX ou de decisão técnica/contratos de arquitetura. O Orquestrador utiliza essas marcações semânticas como gatilhos.
   * **🛑 PARADA (Priorização)**: O Orquestrador solicitará a priorização e selecionará **APENAS UMA Feature** por vez (WIP=1).
3. **Aguardar a Triagem Granular e Aprovação**: O PO aguarda enquanto UX e Arquitetura refinam a Feature Única escolhida (quando aplicável) e o Orquestrador conduz a validação ditada pelo projeto alvo.
   * **🛑 PARADA (Aprovação de Escopo da Feature)**: O Orquestrador submete o escopo da Feature para a regra de validação do projeto alvo.
4. **Desdobrar as Histórias de Usuário**: SOMENTE após a aprovação anterior, o PO desdobra os arquivos de Histórias de Usuário (US) **exclusivamente daquela Feature selecionada** e atualiza os vínculos correspondentes no controle de Backlog do projeto.
   * **🛑 PARADA (Aprovação da Entrega Ágil)**: O Orquestrador submete as Histórias de Usuário para a regra de transição de fase do projeto alvo. Somente após isso o Developer será acionado.

### Diretrizes de Conteúdo e Fidelidade ao Template Local
Ao redigir cada Feature e cada História de Usuário:
- **Subordinação Estrutural Total ao Template do Projeto**: A estrutura de seções, os metadados de Frontmatter YAML, os vínculos de rastreabilidade e os valores de `status` permitidos devem seguir **100% o template e o schema definidos no projeto alvo**.
- **Qualidade Semântica do Conteúdo** (aplicada dentro das seções previstas pelo template do projeto):
  - **Narrativa Ágil**: Persona, ação e benefício claramente delimitados.
  - **Regras de Negócio e Contratos**: Validações, tratamentos de exceção e referências aos contratos/schemas definidos pelo Tech Lead.
  - **Referências Visuais**: Vínculo com os protótipos e jornadas gerados pelo UX Designer e seus estados de interface (quando aplicável).
  - **Critérios de Aceitação BDD (Gherkin)**: Cenários testáveis e determinísticos (`Dado / Quando / Então` ou equivalente do template) cobrindo fluxo principal, dados inválidos e casos de borda.
  - **Diretrizes de Teste e Restrições**: Comandos/alvos de verificação e limites explícitos de escopo/implementação.
5. Salve todos os artefatos e matrizes atualizadas nos diretórios designados pelo manifesto do projeto.

---

## 4. Submissão para Transição
Apresente o resumo dos artefatos de produto gerados/atualizados e submeta o conjunto para o rito de validação e transição de fase definido no manifesto do projeto atual.

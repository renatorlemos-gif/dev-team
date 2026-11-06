---
name: prototipacao-ui
description: Skill do Agente UX / Product Designer. Constrói protótipos visuais interativos e elabora a Jornada do Usuário conforme o Design System e governança do projeto alvo.
---

# Habilidade: Prototipação UX & Jornada do Usuário

Esta habilidade é utilizada pelo **UX / Product Designer** para converter os requisitos em artefatos de experiência do usuário: **jornada do usuário** e **protótipos de interface funcionais e interativos**.

> **Pré-requisito:** Esta skill é acionada na **Triagem Macro (Requisitos/PRD)** ou na **Triagem Granular (Micro-Triage de Feature)** sempre que a avaliação semântica de impacto indicar necessidade de design de experiência, jornada ou refinamento visual/interface.
> **🛑 REGRA ANTI-BATCHING:** Na etapa de Triagem Granular, você deve atuar EXCLUSIVAMENTE sobre a ÚNICA Feature selecionada na etapa de priorização, criando protótipos de tela apenas para o escopo estrito desta Feature específica. É proibido prototipar múltiplas Features em lote.

---

## 1. Bootstrap Obrigatório (Primeiro Passo)
1. Leia a governança do projeto alvo acessando o arquivo `AGENTS.md` (ou `AI_GOVERNANCE.md`) na raiz do repositório.
2. Localize no manifesto do projeto:
   - Os artefatos e templates mapeados para UX / Product Design (ex: Jornada do Usuário).
   - As diretrizes de Design System, componentes e stack tecnológica de prototipação adotadas pelo projeto.
   - Os diretórios de destino para jornadas UX e protótipos no repositório.
3. Leia integralmente os templates e diretrizes de design do projeto antes de gerar qualquer artefato.

---

## 2. Elaboração da Jornada do Usuário

1. Analise os documentos de requisitos para compreender personas, dores e fluxos de interação.
2. Utilize estritamente o template de Jornada do Usuário apontado pelo manifesto do projeto (respeitando suas seções, frontmatter e status válidos).
3. Mapeie todas as etapas, estados emocionais/cognitivos, pontos de contato e fluxos previstos no template.
4. Salve o documento no diretório designado pelo manifesto do projeto.

---

## 3. Construção do Protótipo Funcional

### A. Subordinação ao Design System e Stack do Projeto
1. **Regra Primária (Padrão do Projeto):** Construa o protótipo utilizando estritamente a estrutura de arquivos, biblioteca/framework, configuração de estilos e diretrizes de componentes definidos no manifesto (`AGENTS.md`) ou na documentação de Design System do projeto alvo.
2. **Regra de Fallback (Projetos sem Diretriz de Prototipação):** Somente caso o projeto alvo seja omisso quanto à stack ou estrutura de protótipos, gere o protótipo em uma pasta dedicada (`[diretorio-de-prototipos]/[slug-da-feature]/`) contendo um `README.md` e um arquivo `index.html` autocontido (standalone) executável diretamente no navegador.

### B. Cobertura Obrigatória de Estados de Tela
Independentemente da tecnologia adotada pelo projeto, todo protótipo de tela deve demonstrar de forma clara e navegável:
1. **Estado Padrão / Vazio:** A tela inicial antes da entrada de dados.
2. **Estado Carregando (Loading):** Skeletons, spinners ou desabilitação de controles durante processamento.
3. **Estado de Validação / Erro:** Destaque de campos inválidos e mensagens de erro/alerta.
4. **Estado de Sucesso:** Confirmação visual ou transição para a próxima etapa do fluxo.

---

## 4. Finalização e Vínculo

1. Salve todos os artefatos nos diretórios designados pelo manifesto do projeto.
2. Apresente os protótipos e a jornada ao usuário com links diretos para visualização.
3. Submeta os artefatos para o rito de validação e transição de fase estipulado no manifesto do projeto atual.

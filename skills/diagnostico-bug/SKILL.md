---
name: diagnostico-bug
description: Conduz o diagnóstico estruturado de erros e bugs, gerando a especificação do bug com payload, causa raiz e roteiro TDD Red/Green para o Developer.
---

# Habilidade: Diagnóstico Estruturado de Bugs

Esta habilidade é utilizada quando uma falha, exceção ou comportamento anômalo é relatado, garantindo que o time não tente correções às cegas sem teste de regressão.

---

## 1. Bootstrap Obrigatório (Primeiro Passo)
1. Leia a governança do projeto alvo acessando o arquivo `AGENTS.md` (ou `AI_GOVERNANCE.md`) na raiz do repositório.
2. Verifique no manifesto do projeto como defeitos, incidentes ou bugs são documentados e rastreados (identificando se existe um template/diretório específico para bugs ou se correções utilizam o fluxo padrão de itens de trabalho/histórias do projeto).

---

## 2. Coleta e Triagem do Erro
Ao receber um relato de erro:
1. Obtenha do usuário ou dos logs:
   - Comportamento atual observado vs Comportamento esperado.
   - Stacktrace, logs de erro ou código HTTP retornado.
   - Dados de entrada exatos (payload JSON, query params ou parâmetros) que causam a falha.
2. Identifique a severidade (Low, Medium, High, Critical).

---

## 3. Registro do Diagnóstico do Bug
1. Estruture o diagnóstico cobrindo:
   - Os passos determinísticos de reprodução.
   - O payload/input isolado causador do erro.
   - O módulo e função provável da causa raiz no código-fonte.
   - As diretrizes de teste de regressão (TDD Red/Green).
   - As restrições da correção (proibição de captura silenciosa de exceções ou quebra de contratos públicos).
2. **Forma de Registro Governada pelo Projeto**:
   - **Se o manifesto do projeto definir um artefato/template dedicado para Bugs**: Leia o template correspondente e salve o arquivo no diretório e com a nomenclatura estipulados pelo projeto.
   - **Se o manifesto do projeto NÃO definir um tipo de artefato exclusivo para Bugs**: **Não crie arquivos avulsos não mapeados** nos diretórios governados do projeto. Registre o diagnóstico utilizando o artefato de item de trabalho corretivo previsto pela governança local (ou apresente o diagnóstico técnico estruturado conforme o fluxo de correção definido no `AGENTS.md`).

---

## 4. Repasse ao Developer (TDD Red/Green)
1. Notifique o Orquestrador para acionar o Developer com a referência do arquivo gerado:
   > *"Especificação de bug gerada e estruturada. Developer, consulte a especificação e execute o ciclo Red/Green: crie o teste de falha primeiro e aplique a correção mínima necessária."*

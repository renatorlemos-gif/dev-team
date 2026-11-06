---
name: redacao-atas
description: Skill do Agente Redator de Atas. Transforma registros brutos de reunião (transcrição, notas, VTT, texto) em atas padronizadas, fiéis ao que foi dito e aderentes ao template, ao schema e ao validador designados pelo manifesto do projeto alvo.
---

# Habilidade: Redação de Atas de Reunião

Esta habilidade é utilizada pelo **Redator de Atas** para converter registros brutos de reunião em atas padronizadas, consumíveis por outros agentes e por pessoas. O Redator é um executor "burro" e agnóstico: **não conhece** formato de ata, nomes de campos, seções, prefixos, status, pastas, nomenclatura ou comandos de validação. Tudo isso vem exclusivamente do manifesto do projeto alvo e dos templates, schemas e validadores que ele indicar.

> **ATENÇÃO:** Se esta skill e o manifesto do projeto divergirem, **o manifesto vence**. O Redator **NÃO aprova** atas, **NÃO decide** nada e **NÃO cria** arquivos proprietários no projeto alvo.

---

## 1. Bootstrap Obrigatório (Primeiro Passo)

1. Leia a governança do projeto alvo acessando o arquivo `AGENTS.md` (ou `AI_GOVERNANCE.md`) na raiz do repositório.
2. Mapeie **semanticamente, por capacidade e não por nome**, qual papel do manifesto é responsável por registrar/estruturar atas de reunião.
3. Identifique, exclusivamente a partir do que o projeto designar:
   - o **template** da ata;
   - o **diretório de destino**;
   - a **regra de nomenclatura**;
   - o **status inicial** do ciclo de vida;
   - o **schema** (se houver);
   - o **comando de validação** (se houver);
   - a regra de **imutabilidade/correção** de atas aprovadas;
   - o status que designa uma ata como **aprovada**.
4. Leia o template **integralmente** antes de redigir.

### Caso sem mapeamento (PARE)
Se o manifesto **não atribuir** esse papel a ninguém **nem** indicar template de ata: **PARE imediatamente**. Informe ao usuário/Orquestrador que o projeto não define o padrão de atas. **Não improvise formato, não invente pasta e não crie nenhum arquivo.**

---

## 2. Entrada

1. Localize o registro bruto (transcrição, notas, VTT, texto) indicado pelo usuário. Se nenhum foi indicado, **pergunte**.
2. **Nunca altere, renomeie ou mova** o arquivo bruto.
3. Referencie o registro bruto na ata conforme o campo/regra do template.

---

## 3. Elicitação Mínima

1. Pergunte **apenas** o que o registro não responde e o template exige (por exemplo: título, data, projeto, participantes).
2. Se faltar dado obrigatório, **pergunte**. **Não deduza.**

---

## 4. Fidelidade ao Registro

1. Registre **apenas o que foi efetivamente dito**.
2. É **PROIBIDO** inventar decisões, requisitos, responsáveis, prazos ou números.
3. Distinga rigorosamente o que foi **decidido** do que foi apenas **proposto e não aprovado**: uma proposta **nunca** pode ser registrada como decisão ou requisito.
4. Lacunas e pontos sem resposta devem ser registrados como dúvida/pendência, **no vocabulário do template**.
5. Em caso de ambiguidade sobre se algo foi decidido, trate como não decidido e registre como dúvida/pendência.

---

## 5. Status e Aprovação

1. Gere **sempre** no status inicial definido pelo projeto.
2. É **PROIBIDO** preencher campos de aprovação ou promover o status. A aprovação é **exclusivamente humana**.

---

## 6. Imutabilidade

1. **Nunca** edite silenciosamente uma ata já aprovada.
2. A correção de ata aprovada segue a regra do projeto (em geral, novo documento). Se o manifesto não definir a regra, **pergunte** ao usuário.

---

## 7. Consumo de Atas Existentes

Ao ler atas existentes como insumo para outros papéis, considere **apenas** as que estiverem no status que o projeto designar como aprovado. Ignore as demais (ou sinalize-as como não aprovadas).

---

## 8. Validação Antes de Entregar

1. Execute o validador/linter que o manifesto indicar e corrija a ata até passar.
2. Se nenhum validador for indicado, confira manualmente a ata contra o template e **declare isso na entrega**.

---

## 9. Entrega

1. Salve a ata no caminho e com o nome ditados pelo manifesto.
2. Informe ao usuário: o **caminho** do arquivo, os **itens que ficaram como dúvida/pendência** e que a ata **aguarda aprovação humana**. Informe também o resultado da validação.
3. **NÃO** faça commit, push, abertura de PR nem aprove qualquer coisa, a menos que o manifesto do projeto atribua isso explicitamente ao papel.
4. Notifique o Orquestrador (quando houver) sobre a conclusão.

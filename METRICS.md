# 📊 Métricas de Acompanhamento de Desenvolvimento

Este documento descreve as métricas adotadas para monitorar o progresso, qualidade e escopo do desenvolvimento do sistema **Triiibo E-commerce** ao longo das sprints.

---

## 📐 Tamanho Funcional — Pontos de Função

O tamanho funcional do sistema foi estimado utilizando a metodologia **Análise de Pontos de Função**, considerando as entradas externas, saídas externas, consultas externas, arquivos lógicos internos e arquivos de interface externa.

| Métrica                               | Valor        |
| ------------------------------------- | ------------ |
| Pontos de Função Não Ajustados (PFNA) | 105 PF       |
| TDI (Total Degree of Influence)       | 41           |
| Fator de Ajuste (FA)                  | 1,06         |
| **Pontos de Função Ajustados (PFA)**  | **111,3 PF** |

> Fórmula aplicada: `FA = (TDI × 0,01) + 0,65` → `PFA = PFNA × FA`
> Os dados foram detalhados no arquivo de estimativa de pontos de função disponível em [`Pontos de Funcao`](./docs/Pontos%20de%20Função.docx).

---

## 📈 Métricas de Progresso

Métricas utilizadas para acompanhar o ritmo de entrega a cada sprint.

| Métrica               | Descrição                                       | Como medir                                                          |
| --------------------- | ----------------------------------------------- | ------------------------------------------------------------------- |
| **Velocity**          | Story points entregues por sprint               | Somar SP das tarefas com status _Concluído_ ao final de cada sprint |
| **Taxa de conclusão** | % de tarefas concluídas em relação ao planejado | `(tarefas concluídas / tarefas planejadas) × 100`                   |
| **Burndown**          | SP restantes por dia dentro da sprint           | Gerado automaticamente pelo Jira; referência visual no repositório  |
| **Cobertura de RFs**  | Requisitos funcionais implementados             | `(RFs implementados / 20 RFs totais) × 100`                         |

> Burndown Chart Simulado para a Sprint 1 está disponível em [`Burndown Chart`](./docs/Burndown%20Chart%20Sprint%201.png).

---

## 🐛 Métricas de Qualidade

Métricas para avaliar a aderência do sistema aos requisitos definidos.

| Métrica                         | Descrição                               | Como medir                                                     |
| ------------------------------- | --------------------------------------- | -------------------------------------------------------------- |
| **Taxa de aprovação de testes** | % de casos de teste que passaram        | `(casos aprovados / total de casos executados) × 100`          |
| **Densidade de bugs**           | Bugs encontrados por sprint             | Contagem de issues abertas com label `bug` no GitHub           |
| **Cobertura de testes**         | % dos RFs cobertos pelo plano de testes | Mapeamento dos 60 casos de teste documentados contra os 20 RFs |

> O plano de testes completo (60 casos de teste cobrindo RF01–RF20, com happy path, sad path e bad path) está documentado em [`Plano de Caso de Teste`](./docs/Plano%20de%20Casos%20de%20Teste.docx).

---

## 🎯 Métricas de Escopo

Métricas para controlar variações no escopo ao longo do projeto.

| Métrica            | Descrição                                               | Como medir                                                               |
| ------------------ | ------------------------------------------------------- | ------------------------------------------------------------------------ |
| **Scope creep**    | Tarefas adicionadas ao backlog após o início do projeto | Contagem de issues criadas após a sprint 1 sem origem no backlog inicial |
| **Variação de SP** | Diferença entre SP planejados e realizados              | `SP planejados − SP entregues` por sprint                                |

---

## 🛠️ Ferramentas Utilizadas

- **Jira** — gestão do backlog, sprints e geração do burndown chart (Vale ressaltar que o anexo do burndown chart do projeto não foi gerado no Jira, mas sim criado manualmente. Por ser uma simulação feita em um dia só o Jira não consegue gerar um adequado).
- **GitHub** — controle de versão, rastreio de bugs via issues e CI/CD via GitHub Actions
- **Planilha de Cálculo de Pontos de Função** — estimativa de tamanho funcional (IFPUG)

---

> Documento elaborado como parte da disciplina de Engenharia de Software — 2026.

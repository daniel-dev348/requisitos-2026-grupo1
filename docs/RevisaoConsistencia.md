# Revisão de Consistência — UML × SRS
## Sistema de Preparação para o ENADE

**Data:** 02/06/2026 | **Diagrama referenciado:** v3 (corrigido) | **SRS referenciado:** v3

---

## 1. Mapeamento UC → RF

| UC (Diagrama v3) | Ator correto | Módulo | RFs Cobertos | Status |
|-----------------|-------------|--------|-------------|--------|
| UC-01 — Cadastrar-se e Login | Todos | Acesso | RF-01 | ✅ Consistente |
| UC-10 — Recuperar Senha | Todos | Acesso | RF-02 | ✅ Consistente |
| UC-11 — Cadastrar Turmas | **Coordenador** | Gestão de Usuários | RF-03 | ✅ Corrigido (era Administrador) |
| UC-12 — Cadastrar Alunos | **Coordenador** | Gestão de Usuários | RF-04 | ✅ Corrigido (era Administrador) |
| UC-13 — Cadastrar Professores | **Coordenador** | Gestão de Usuários | RF-05 | ✅ Corrigido (era Administrador) |
| UC-09 — Registrar Questões | Professor | Banco de Questões | RF-06 | ✅ Consistente |
| UC-14 — Validar Questão | Professor | Banco de Questões | RF-07 | ✅ Consistente |
| UC-02 — Consultar Questões | Estudante | Banco de Questões | RF-08 | ✅ Consistente |
| UC-04 — Visualizar Gabarito | Estudante | Banco / Simulado | RF-09, RF-11 | ✅ Consistente |
| UC-03 — Realizar Simulado | Estudante | Simulados | RF-10, RF-11 | ✅ Consistente |
| UC-05 — Ver Desempenho | Estudante | Desempenho | RF-12 | ✅ Consistente |
| UC-07 — Acompanhar por Turma | Coordenador | Relatórios | RF-13 | ✅ Consistente |
| UC-06 — Participar do Fórum | Estudante | Fórum | RF-14 | ✅ Consistente |

---

## 2. Mapeamento RF → UC (verificação inversa)

| Requisito | UC no Diagrama | Ator correto | Coberto? |
|-----------|---------------|-------------|----------|
| RF-01 | UC-01 | Todos | ✅ |
| RF-02 | UC-10 | Todos | ✅ |
| RF-03 | UC-11 | **Coordenador** | ✅ |
| RF-04 | UC-12 | **Coordenador** | ✅ |
| RF-05 | UC-13 | **Coordenador** | ✅ |
| RF-06 | UC-09 | Professor | ✅ |
| RF-07 | UC-14 | Professor | ✅ |
| RF-08 | UC-02 | Estudante | ✅ |
| RF-09 | UC-04 | Estudante | ✅ |
| RF-10 | UC-03 | Estudante | ✅ |
| RF-11 | UC-03 / UC-04 | Estudante | ✅ |
| RF-12 | UC-05 | Estudante | ✅ |
| RF-13 | UC-07 | Coordenador | ✅ |
| RF-14 | UC-06 | Estudante | ✅ |

---

## 3. Verificação de Atores

| Ator no Diagrama v3 | Papel no sistema | RFs que acessa |
|--------------------|-----------------|----------------|
| Administrador (TI) | Infraestrutura técnica — não cadastra usuários da plataforma | RF-01, RF-02 (acesso geral) |
| Coordenador | Libera acesso de alunos e professores; acompanha indicadores | RF-01, RF-02, **RF-03, RF-04, RF-05**, RF-13 |
| Professor | Após acesso liberado pelo Coordenador: registra e valida questões | RF-01, RF-02, RF-06, RF-07 |
| Estudante | Após acesso liberado pelo Coordenador: usa a plataforma | RF-01, RF-02, RF-08 a RF-14 |

---

## 4. Relacionamentos UML × Requisitos

| Relacionamento | Tipo UML | Requisito / Regra |
|---------------|----------|------------------|
| UC-11/12/13 → UC-01 | «include» | Coordenador deve estar autenticado para cadastrar (RF-01 pré-condição) |
| UC-04 → UC-02 | «extend» | Gabarito é extensão de consultar questão — condição: questão respondida (RN-04) |
| UC-04 → UC-03 | «extend» | Gabarito é extensão de realizar simulado — condição: simulado encerrado (RN-04) |

---

## 5. Regras de Negócio no Diagrama

| Regra | UC onde anotar | Forma sugerida |
|-------|---------------|----------------|
| RN-01 — Fonte INEP/validada | UC-09, UC-02, UC-03 | Nota/constraint |
| RN-02 — Estrutura do simulado | UC-03 | Pré-condição |
| RN-03 — Cronômetro sem pausa | UC-03 | Restrição no fluxo principal |
| RN-04 — Gabarito pós-resposta | UC-04 (condição do extend) | Condição de guarda |
| RN-05 — Anonimização | UC-07 | Pré-condição |
| RN-06 — Fórum autenticado | UC-06 | Pré-condição |
| RN-07 — Validação por par | UC-14 | Constraint: validador ≠ autor |

---

## 6. Correções aplicadas nesta versão

| Item corrigido | Versão anterior (v2) | Versão atual (v3) |
|---------------|---------------------|------------------------------|
| Ator de UC-11 | Administrador | **Coordenador** |
| Ator de UC-12 | Administrador | **Coordenador** |
| Ator de UC-13 | Administrador | **Coordenador** |
| Papel do Administrador | Cadastrava usuários da plataforma | Apenas infraestrutura técnica (TI) |
| Papel do Coordenador | Só relatórios | Gestão de usuários + relatórios |

---

## 7. Conclusão

| Indicador | Resultado |
|-----------|-----------|
| Total de RFs no SRS v4.1 | 14 |
| RFs cobertos por UC no diagrama v3 | 14 |
| Total de UCs no diagrama v3 | 13 |
| UCs com RF correspondente | 13 |
| Inconsistências encontradas | 0 |
| Correções aplicadas nesta versão | 3 (atores de UC-11, UC-12 e UC-13) |


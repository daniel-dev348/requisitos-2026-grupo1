# Software Requirements Specification (SRS)
## Sistema de Preparação para o ENADE
**Padrão IEEE 830**

---

## Histórico de Versões

| Data | Versão | Descrição | Autor |
|------|--------|-----------|-------|
| 28/04/2026 | 1.0 | Criação do Documento de Visão (VD) | Equipe de Desenvolvimento |
| 30/04/2026 | 2.0 | Atualização das seções de personas, restrições e glossário | Equipe de Desenvolvimento |
| 02/06/2026 | 3.0 | Evolução para SRS (IEEE 830): especificação detalhada de requisitos | Equipe de Desenvolvimento |
| 02/06/2026 | 4.0 | Atualização dos RFs e rastreabilidade com base no Diagrama de Casos de Uso v2 | Equipe de Desenvolvimento |

---

## 1. Introdução

### 1.1 Propósito

Este documento especifica os requisitos de software do **Sistema de Preparação para o ENADE**, uma plataforma web destinada a apoiar estudantes de graduação na preparação para o Exame Nacional de Desempenho dos Estudantes. O documento segue o padrão IEEE 830 e tem como público-alvo a equipe de desenvolvimento, os professores orientadores e as coordenações de curso envolvidas no projeto.

### 1.2 Escopo

O sistema, denominado **EnadePREP**, é uma plataforma centralizada que oferece:

- Banco de questões das provas anteriores do ENADE, organizadas por ano, curso e área de conhecimento;
- Cadastro e validação de questões por professores;
- Simulados cronometrados com gabarito comentado;
- Estatísticas de desempenho individual por área;
- Fórum de discussão por questão;
- Painel de acompanhamento para coordenadores de curso;
- Gestão administrativa de turmas, alunos e professores.

O sistema **não contempla**, na versão 1.0:
- Gamificação (rankings, medalhas, pontuação);
- Integração com sistemas acadêmicos institucionais (ex.: SIGAA, Moodle).

### 1.3 Definições, Acrônimos e Abreviações

| Termo | Definição |
|-------|-----------|
| ENADE | Exame Nacional de Desempenho dos Estudantes |
| INEP | Instituto Nacional de Estudos e Pesquisas Educacionais Anísio Teixeira |
| SRS | Software Requirements Specification |
| UML | Unified Modeling Language |
| RF | Requisito Funcional |
| RNF | Requisito Não Funcional |
| RN | Regra de Negócio |
| LGPD | Lei Geral de Proteção de Dados (Lei nº 13.709/2018) |
| UC | Use Case (Caso de Uso) |
| Gabarito Comentado | Resposta correta com justificativa detalhada |
| Formação Geral | Componente do ENADE avaliando competências gerais |
| Conhecimento Específico | Componente do ENADE avaliando conteúdo da área de formação |

### 1.4 Referências

- IEEE Std 830-1998 — IEEE Recommended Practice for Software Requirements Specifications
- Lei nº 13.709/2018 — Lei Geral de Proteção de Dados (LGPD)
- Portal INEP: www.inep.gov.br (fonte das provas oficiais do ENADE)
- Documento de Visão da Demanda (VD) — versão 2.0, 30/04/2026
- Diagrama de Casos de Uso — Sistema de Preparação para o ENADE v2, UNIFOR Grupo 1, 2026

### 1.5 Visão Geral do Documento

- **Seção 2:** Descrição geral do sistema (contexto, usuários, restrições).
- **Seção 3:** Requisitos específicos (funcionais, não funcionais e regras de negócio).
- **Apêndice A:** Rastreabilidade RF ↔ UC ↔ RN.

---

## 2. Descrição Geral

### 2.1 Perspectiva do Produto

O EnadePREP é um sistema novo, independente, sem integração obrigatória com outros sistemas institucionais na versão 1.0. Será acessado via navegador web (desktop). O sistema opera no modelo cliente-servidor, com front-end responsivo e back-end com API REST, conectado a um banco de dados relacional.

```
[Estudante / Professor / Coordenador / Administrador]
        |
   [Navegador Web]
        |
   [Front-end — Interface]
        |
   [API REST — Back-end]
        |
   [Banco de Dados]
```

### 2.2 Funções do Produto

1. Cadastro e autenticação de usuários (todos os perfis)
2. Gestão administrativa de turmas, alunos e professores
3. Registro e validação de questões por professores
4. Consulta e filtragem de questões do banco ENADE
5. Realização de simulados cronometrados
6. Exibição de gabarito comentado pós-resposta
7. Visualização de estatísticas de desempenho individual
8. Painel de desempenho agregado para coordenadores
9. Participação em fórum de discussão por questão

### 2.3 Características dos Usuários

| Usuário | Perfil Tecnológico | Frequência de Uso | Necessidades Principais |
|---------|--------------------|-------------------|------------------------|
| Estudante | Intermediário; smartphone e computador, familiaridade com Moodle | Alta — diária ou 3x/semana no pré-ENADE | Questões organizadas, simulados, feedback de erros |
| Professor | Intermediário/Avançado; familiaridade com ferramentas acadêmicas | Média — cadastro e validação de questões periodicamente | Inserir e validar questões no banco |
| Coordenador de Curso | Intermediário; ferramentas de gestão e planilhas | Média — semanal/mensal, maior intensidade no pré-ENADE | Relatórios visuais e sintéticos por turma |
| Administrador | Avançado; gerencia o sistema | Alta — gestão contínua de usuários e turmas | Cadastrar turmas, alunos e professores no sistema |

### 2.4 Restrições Gerais

- O sistema é um projeto conceitual — não haverá implementação de código funcional nesta fase.
- O banco de questões é composto exclusivamente por provas oficiais do INEP ou questões cadastradas e validadas por professores habilitados.
- Funcionalidades de gamificação estão fora do escopo da versão 1.0.
- O sistema deve estar em conformidade com a LGPD (Lei nº 13.709/2018).
- A documentação técnica segue os padrões IEEE 830 e notação UML.

### 2.5 Premissas e Dependências

**Premissas:**
- As provas do ENADE disponibilizadas pelo INEP são de acesso público e podem ser usadas para fins educacionais.
- Os estudantes possuem acesso à internet e a dispositivos compatíveis.
- As coordenações demonstrarão interesse em adotar a plataforma.

**Dependências:**
- Portal INEP (www.inep.gov.br) — fonte primária das questões.
- Ferramentas de modelagem UML (Lucidchart, Draw.io ou Astah).
- Ferramentas de prototipação (Figma, Adobe XD ou Balsamiq).

---

## 3. Requisitos Específicos

### 3.1 Requisitos Funcionais

Os requisitos funcionais estão organizados por módulo, alinhados ao Diagrama de Casos de Uso v2.

---

#### Módulo 1 — Acesso (Todos os Perfis)

---

**RF-01 — Cadastrar-se e realizar login**
- **Descrição:** O sistema deve permitir que novos usuários se cadastrem informando nome completo, e-mail, senha e perfil. Usuários já cadastrados devem conseguir realizar login com e-mail e senha. Em caso de credenciais inválidas, o sistema exibe mensagem de erro genérica.
- **Atores:** Estudante, Professor, Coordenador, Administrador
- **Prioridade:** Alta
- **UC Associado:** UC-01 — Cadastrar-se e Login

---

**RF-02 — Recuperar senha**
- **Descrição:** O sistema deve oferecer mecanismo de recuperação de senha via e-mail cadastrado, enviando link temporário para redefinição.
- **Atores:** Estudante, Professor, Coordenador, Administrador
- **Prioridade:** Média
- **UC Associado:** UC-10 — Recuperar Senha

---

#### Módulo 2 — Gestão de Usuários (Administrador / Coordenador)

---

**RF-03 — Cadastrar turmas**
- **Descrição:** O sistema deve permitir que o Administrador cadastre turmas no sistema, associando-as a um curso e período letivo.
- **Atores:** Administrador
- **Prioridade:** Alta
- **UC Associado:** UC-11 — Cadastrar Turmas

---

**RF-04 — Cadastrar alunos**
- **Descrição:** O sistema deve permitir que o Administrador cadastre alunos, vinculando-os a uma turma e curso.
- **Atores:** Administrador
- **Prioridade:** Alta
- **UC Associado:** UC-12 — Cadastrar Alunos

---

**RF-05 — Cadastrar professores**
- **Descrição:** O sistema deve permitir que o Administrador cadastre professores, habilitando-os a registrar e validar questões no banco.
- **Atores:** Administrador
- **Prioridade:** Alta
- **UC Associado:** UC-13 — Cadastrar Professores

---

#### Módulo 3 — Banco de Questões (Professor)

---

**RF-06 — Registrar questões e competências**
- **Descrição:** O sistema deve permitir que professores cadastrados registrem questões no banco, informando: enunciado, alternativas, gabarito, comentário explicativo, área de conhecimento, competência associada e fonte (ano/prova INEP ou autoral).
- **Atores:** Professor
- **Prioridade:** Alta
- **UC Associado:** UC-09 — Registrar Questões e Competências

---

**RF-07 — Validar questão no banco**
- **Descrição:** O sistema deve permitir que professores revisem e validem questões registradas por outros professores antes de sua disponibilização aos estudantes. Uma questão só fica disponível no banco após validação.
- **Atores:** Professor
- **Prioridade:** Alta
- **UC Associado:** UC-14 — Validar Questão no Banco

---

#### Módulo 4 — Banco de Questões (Estudante)

---

**RF-08 — Consultar banco de questões**
- **Descrição:** O sistema deve permitir que o estudante visualize e filtre questões do banco por: ano, curso, área de conhecimento e componente (Formação Geral ou Conhecimento Específico).
- **Atores:** Estudante
- **Prioridade:** Alta
- **UC Associado:** UC-02 — Consultar Banco de Questões

---

**RF-09 — Visualizar gabarito comentado**
- **Descrição:** O sistema deve exibir, após o estudante responder uma questão no modo banco, a alternativa correta com explicação detalhada. Durante o simulado, o gabarito é inacessível.
- **Atores:** Estudante
- **Prioridade:** Alta
- **UC Associado:** UC-04 — Visualizar Gabarito *(extend de UC-02 e UC-03)*

---

#### Módulo 5 — Simulados

---

**RF-10 — Realizar simulado cronometrado**
- **Descrição:** O sistema deve permitir que o estudante configure e realize um simulado com cronômetro regressivo visível. O estudante seleciona quantidade de questões, ano(s) e área(s). Ao esgotar o tempo, o simulado é encerrado automaticamente.
- **Atores:** Estudante
- **Prioridade:** Alta
- **UC Associado:** UC-03 — Realizar Simulado

---

**RF-11 — Exibir resultado do simulado**
- **Descrição:** Ao encerrar o simulado, o sistema deve exibir: percentual de acertos geral e por área, tempo utilizado e gabarito comentado de cada questão.
- **Atores:** Estudante
- **Prioridade:** Alta
- **UC Associado:** UC-03 — Realizar Simulado / UC-04 — Visualizar Gabarito *(extend)*

---

#### Módulo 6 — Desempenho

---

**RF-12 — Ver desempenho individual**
- **Descrição:** O sistema deve gerar e exibir para o estudante: histórico de simulados, percentual de acertos por área, evolução ao longo do tempo e questões com maior taxa de erro.
- **Atores:** Estudante
- **Prioridade:** Alta
- **UC Associado:** UC-05 — Ver Desempenho Individual

---

**RF-13 — Acompanhar indicadores por turma**
- **Descrição:** O sistema deve disponibilizar ao Coordenador um painel com desempenho agregado por turma: média de acertos por área, distribuição de desempenho e comparativo entre períodos. Todos os dados devem ser anonimizados.
- **Atores:** Coordenador de Curso
- **Prioridade:** Média
- **UC Associado:** UC-07 — Acompanhar Indicadores por Turma

---

#### Módulo 7 — Fórum de Discussão

---

**RF-14 — Participar do fórum**
- **Descrição:** O sistema deve permitir que estudantes autenticados publiquem e visualizem comentários no fórum vinculado a cada questão, em ordem cronológica.
- **Atores:** Estudante
- **Prioridade:** Média
- **UC Associado:** UC-06 — Participar do Fórum

---

### 3.2 Requisitos Não Funcionais

---

**RNF-01 — Disponibilidade**
- **Descrição:** A plataforma deve estar disponível 24/7, com tolerância a indisponibilidade planejada de até 2 horas por semana entre 02h e 04h.
- **Categoria:** Disponibilidade | **Prioridade:** Alta

---

**RNF-02 — Desempenho**
- **Descrição:** O sistema deve responder a requisições de consulta de questões em até 3 segundos, com conexão mínima de 5 Mbps e carga de até 500 usuários simultâneos.
- **Categoria:** Desempenho | **Prioridade:** Alta

---

**RNF-03 — Segurança e Privacidade (LGPD)**
- **Descrição:** O sistema deve estar em conformidade com a Lei nº 13.709/2018. Dados pessoais devem ser armazenados com criptografia. O consentimento deve ser obtido no cadastro. O painel da coordenação exibe apenas dados anonimizados.
- **Categoria:** Segurança / Privacidade | **Prioridade:** Alta

---

**RNF-04 — Usabilidade**
- **Descrição:** A interface deve ser responsiva (telas a partir de 320px) e permitir iniciar um simulado em no máximo 3 cliques a partir da tela inicial.
- **Categoria:** Usabilidade | **Prioridade:** Alta

---

**RNF-05 — Portabilidade**
- **Descrição:** O sistema deve ser compatível com Chrome, Firefox, Safari e Edge (duas versões mais recentes) e dispositivos móveis iOS e Android.
- **Categoria:** Portabilidade | **Prioridade:** Média

---

**RNF-06 — Manutenibilidade**
- **Descrição:** O código-fonte deve seguir padrões documentados, com cobertura mínima de 70% de testes automatizados nos módulos críticos (autenticação, simulado, desempenho).
- **Categoria:** Manutenibilidade | **Prioridade:** Média

---

**RNF-07 — Conformidade Técnica**
- **Descrição:** A documentação técnica do projeto deve seguir os padrões IEEE 830 e notação UML para todos os diagramas entregues.
- **Categoria:** Conformidade | **Prioridade:** Alta

---

### 3.3 Regras de Negócio

---

**RN-01 — Fonte do banco de questões**
- **Descrição:** O banco de questões deve ser composto por provas oficiais do INEP ou por questões cadastradas por professores habilitados e validadas por pelo menos um outro professor antes da publicação.
- **Requisitos relacionados:** RF-06, RF-07, RF-08, RF-10

---

**RN-02 — Estrutura do simulado**
- **Descrição:** O simulado deve seguir a estrutura oficial do ENADE (Formação Geral + Conhecimento Específico), com distribuição proporcional de questões ao curso selecionado.
- **Requisitos relacionados:** RF-10, RF-11

---

**RN-03 — Cronômetro não pode ser pausado**
- **Descrição:** Uma vez iniciado, o cronômetro do simulado não pode ser pausado. O simulado é encerrado automaticamente ao término do tempo ou por ação manual do estudante.
- **Requisitos relacionados:** RF-10

---

**RN-04 — Gabarito disponível apenas após resposta**
- **Descrição:** O gabarito comentado só pode ser visualizado após o estudante responder a questão (modo banco) ou após encerramento do simulado. Durante o simulado, o gabarito é inacessível.
- **Requisitos relacionados:** RF-09, RF-11

---

**RN-05 — Anonimização no painel da coordenação**
- **Descrição:** O painel da coordenação exibe exclusivamente dados agregados por turma. É vedada a exibição de desempenho individual nominalmente identificado, em conformidade com a LGPD.
- **Requisitos relacionados:** RF-13, RNF-03

---

**RN-06 — Fórum restrito a usuários autenticados**
- **Descrição:** Somente usuários autenticados podem publicar comentários no fórum. A leitura pode ser liberada para não autenticados a critério da equipe.
- **Requisitos relacionados:** RF-14

---

**RN-07 — Validação de questão por par**
- **Descrição:** Uma questão registrada por um professor só pode ser validada por outro professor diferente do autor. O próprio autor não pode validar sua própria questão.
- **Requisitos relacionados:** RF-07

---

**RN-08 — Gamificação fora do escopo**
- **Descrição:** Funcionalidades de gamificação (rankings, medalhas, pontuação acumulada) estão fora do escopo da versão 1.0.
- **Requisitos relacionados:** N/A

---

## Apêndice A — Rastreabilidade de Requisitos

| Requisito | Descrição Resumida | UC Associado (diagrama v2) | RN Associada |
|-----------|-------------------|---------------------------|--------------|
| RF-01 | Cadastrar-se e login | UC-01 | — |
| RF-02 | Recuperar senha | UC-10 | — |
| RF-03 | Cadastrar turmas | UC-11 | — |
| RF-04 | Cadastrar alunos | UC-12 | — |
| RF-05 | Cadastrar professores | UC-13 | — |
| RF-06 | Registrar questões e competências | UC-09 | RN-01 |
| RF-07 | Validar questão no banco | UC-14 | RN-01, RN-07 |
| RF-08 | Consultar banco de questões | UC-02 | RN-01 |
| RF-09 | Visualizar gabarito comentado | UC-04 | RN-04 |
| RF-10 | Realizar simulado cronometrado | UC-03 | RN-01, RN-02, RN-03 |
| RF-11 | Exibir resultado do simulado | UC-03 / UC-04 | RN-04 |
| RF-12 | Ver desempenho individual | UC-05 | — |
| RF-13 | Acompanhar indicadores por turma | UC-07 | RN-05 |
| RF-14 | Participar do fórum | UC-06 | RN-06 |

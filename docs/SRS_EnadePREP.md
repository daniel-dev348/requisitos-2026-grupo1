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

---

## 1. Introdução

### 1.1 Propósito

Este documento especifica os requisitos de software do **Sistema de Preparação para o ENADE**, uma plataforma web/mobile destinada a apoiar estudantes de graduação na preparação para o Exame Nacional de Desempenho dos Estudantes. O documento segue o padrão IEEE 830 e tem como público-alvo a equipe de desenvolvimento, os professores orientadores e as coordenações de curso envolvidas no projeto.

### 1.2 Escopo

O sistema, denominado **EnadePREP**, é uma plataforma centralizada que oferece:

- Banco de questões das provas anteriores do ENADE, organizadas por ano, curso e área de conhecimento;
- Simulados cronometrados com gabarito comentado;
- Estatísticas de desempenho individual por área;
- Fórum de discussão por questão;
- Painel de acompanhamento para coordenadores de curso.

O sistema **não contempla**, na versão 1.0:
- Gamificação (rankings, medalhas, pontuação);
- Criação de questões próprias fora do acervo INEP;
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

### 1.5 Visão Geral do Documento

O restante deste documento está organizado da seguinte forma:
- **Seção 2:** Descrição geral do sistema (contexto, usuários, restrições).
- **Seção 3:** Requisitos específicos (funcionais, não funcionais e regras de negócio).

---

## 2. Descrição Geral

### 2.1 Perspectiva do Produto

O EnadePREP é um sistema novo, independente, sem integração obrigatória com outros sistemas institucionais na versão 1.0. Será acessado via navegador web (desktop e mobile) e futuramente como aplicativo móvel nativo. O sistema opera no modelo cliente-servidor, com front-end responsivo e back-end com API REST, conectado a um banco de dados relacional.

```
[Estudante / Coordenador]
        |
   [Navegador Web / App Mobile]
        |
   [Front-end — Interface]
        |
   [API REST — Back-end]
        |
   [Banco de Dados]
```

### 2.2 Funções do Produto

As principais funções do sistema são:

1. Cadastro e autenticação de usuários (estudantes e coordenadores)
2. Consulta e filtragem de questões do banco ENADE
3. Realização de simulados cronometrados
4. Exibição de gabarito comentado pós-resposta
5. Visualização de estatísticas de desempenho individual
6. Acesso ao painel de desempenho agregado (coordenadores)
7. Participação em fórum de discussão por questão

### 2.3 Características dos Usuários

| Usuário | Perfil Tecnológico | Frequência de Uso | Necessidades Principais |
|---------|--------------------|-------------------|------------------------|
| Estudante de Graduação | Intermediário; usa smartphone e computador, familiaridade com Moodle | Alta — diária ou 3x/semana no pré-ENADE | Questões organizadas, simulados, feedback de erros |
| Coordenador de Curso | Intermediário; usa ferramentas de gestão e planilhas | Média — semanal/mensal, maior intensidade no pré-ENADE | Relatórios visuais e sintéticos por turma |

### 2.4 Restrições Gerais

- O sistema é um projeto conceitual — não haverá implementação de código funcional nesta fase.
- O banco de questões é composto exclusivamente por provas oficiais do INEP.
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

Os requisitos funcionais estão organizados por módulo do sistema. Cada requisito possui: identificador, descrição, atores envolvidos, prioridade e casos de uso associados.

---

#### Módulo 1 — Gestão de Usuários

---

**RF-01 — Cadastro de usuário**
- **Descrição:** O sistema deve permitir que novos usuários se cadastrem informando nome completo, e-mail, senha, curso de graduação e perfil (estudante ou coordenador).
- **Atores:** Estudante, Coordenador de Curso
- **Prioridade:** Alta
- **UC Associado:** UC-01 — Cadastrar Usuário

---

**RF-02 — Autenticação de usuário**
- **Descrição:** O sistema deve permitir que usuários cadastrados realizem login com e-mail e senha. Em caso de credenciais inválidas, o sistema deve exibir mensagem de erro sem especificar qual campo está incorreto.
- **Atores:** Estudante, Coordenador de Curso
- **Prioridade:** Alta
- **UC Associado:** UC-02 — Autenticar Usuário

---

**RF-03 — Recuperação de senha**
- **Descrição:** O sistema deve oferecer mecanismo de recuperação de senha via e-mail cadastrado, enviando link temporário para redefinição.
- **Atores:** Estudante, Coordenador de Curso
- **Prioridade:** Média
- **UC Associado:** UC-02 — Autenticar Usuário

---

#### Módulo 2 — Banco de Questões

---

**RF-04 — Visualizar questões**
- **Descrição:** O sistema deve permitir que o estudante visualize questões do banco ENADE com enunciado completo, alternativas e identificação de fonte (ano, curso, componente).
- **Atores:** Estudante
- **Prioridade:** Alta
- **UC Associado:** UC-03 — Consultar Banco de Questões

---

**RF-05 — Filtrar questões**
- **Descrição:** O sistema deve permitir que o estudante filtre questões por: ano de aplicação, curso, área de conhecimento e componente (Formação Geral ou Conhecimento Específico). Os filtros podem ser combinados.
- **Atores:** Estudante
- **Prioridade:** Alta
- **UC Associado:** UC-03 — Consultar Banco de Questões

---

**RF-06 — Exibir gabarito comentado**
- **Descrição:** O sistema deve exibir, após o estudante responder uma questão fora do simulado, a alternativa correta com explicação detalhada justificando o gabarito e, quando possível, indicando o erro das demais alternativas.
- **Atores:** Estudante
- **Prioridade:** Alta
- **UC Associado:** UC-03 — Consultar Banco de Questões

---

#### Módulo 3 — Simulados

---

**RF-07 — Configurar simulado**
- **Descrição:** O sistema deve permitir que o estudante configure um simulado selecionando: quantidade de questões, ano(s), área(s) de conhecimento e componente. O sistema deve montar a prova automaticamente com base nos filtros.
- **Atores:** Estudante
- **Prioridade:** Alta
- **UC Associado:** UC-04 — Realizar Simulado

---

**RF-08 — Realizar simulado cronometrado**
- **Descrição:** O sistema deve apresentar o simulado com cronômetro regressivo visível. Ao esgotar o tempo, o simulado deve ser encerrado automaticamente com as respostas até então registradas.
- **Atores:** Estudante
- **Prioridade:** Alta
- **UC Associado:** UC-04 — Realizar Simulado

---

**RF-09 — Exibir resultado do simulado**
- **Descrição:** Ao encerrar o simulado, o sistema deve exibir o resultado com: percentual de acertos geral e por área, tempo utilizado e gabarito comentado de cada questão.
- **Atores:** Estudante
- **Prioridade:** Alta
- **UC Associado:** UC-04 — Realizar Simulado

---

#### Módulo 4 — Desempenho

---

**RF-10 — Visualizar estatísticas individuais**
- **Descrição:** O sistema deve gerar e exibir para o estudante um painel com: histórico de simulados realizados, percentual de acertos por área de conhecimento, evolução de desempenho ao longo do tempo e questões com maior taxa de erro.
- **Atores:** Estudante
- **Prioridade:** Alta
- **UC Associado:** UC-05 — Visualizar Desempenho

---

**RF-11 — Visualizar painel da coordenação**
- **Descrição:** O sistema deve disponibilizar ao coordenador de curso um painel com relatórios de desempenho agregado por turma/curso, exibindo: média de acertos por área, distribuição de desempenho e comparativo entre períodos. Todos os dados devem ser anonimizados.
- **Atores:** Coordenador de Curso
- **Prioridade:** Média
- **UC Associado:** UC-06 — Acompanhar Desempenho da Turma

---

#### Módulo 5 — Fórum de Discussão

---

**RF-12 — Publicar comentário no fórum**
- **Descrição:** O sistema deve permitir que estudantes autenticados publiquem comentários e dúvidas no fórum vinculado a cada questão.
- **Atores:** Estudante
- **Prioridade:** Média
- **UC Associado:** UC-07 — Participar do Fórum

---

**RF-13 — Visualizar discussões do fórum**
- **Descrição:** O sistema deve exibir os comentários do fórum de cada questão em ordem cronológica, identificando o autor pelo nome ou apelido.
- **Atores:** Estudante
- **Prioridade:** Média
- **UC Associado:** UC-07 — Participar do Fórum

---

### 3.2 Requisitos Não Funcionais

---

**RNF-01 — Disponibilidade**
- **Descrição:** A plataforma deve estar disponível 24 horas por dia, 7 dias por semana, com tolerância a indisponibilidade planejada de até 2 horas por semana em horário não comercial (entre 02h e 04h).
- **Categoria:** Disponibilidade
- **Prioridade:** Alta

---

**RNF-02 — Desempenho**
- **Descrição:** O sistema deve responder a requisições de consulta de questões e carregamento de páginas em até 3 segundos, considerando uma conexão de pelo menos 5 Mbps e carga de até 500 usuários simultâneos.
- **Categoria:** Desempenho
- **Prioridade:** Alta

---

**RNF-03 — Segurança e Privacidade (LGPD)**
- **Descrição:** O sistema deve estar em conformidade com a Lei nº 13.709/2018 (LGPD). Dados pessoais dos usuários devem ser armazenados com criptografia. O consentimento do usuário deve ser obtido no cadastro. O painel da coordenação deve exibir apenas dados anonimizados e agregados.
- **Categoria:** Segurança / Privacidade
- **Prioridade:** Alta

---

**RNF-04 — Usabilidade**
- **Descrição:** A interface deve ser intuitiva, com fluxo de no máximo 3 cliques para iniciar um simulado a partir da tela inicial. O sistema deve ser responsivo e funcional em telas a partir de 320px de largura.
- **Categoria:** Usabilidade
- **Prioridade:** Alta

---

**RNF-05 — Portabilidade**
- **Descrição:** O sistema deve ser compatível com os principais navegadores modernos (Chrome, Firefox, Safari e Edge, nas duas versões mais recentes) e com dispositivos móveis iOS e Android.
- **Categoria:** Portabilidade
- **Prioridade:** Média

---

**RNF-06 — Manutenibilidade**
- **Descrição:** O código-fonte deve seguir padrões de desenvolvimento documentados, com cobertura mínima de 70% de testes automatizados nos módulos críticos (autenticação, simulado e desempenho).
- **Categoria:** Manutenibilidade
- **Prioridade:** Média

---

**RNF-07 — Conformidade Técnica**
- **Descrição:** A documentação técnica do projeto deve seguir os padrões IEEE 830 (SRS) e notação UML para todos os diagramas entregues.
- **Categoria:** Conformidade
- **Prioridade:** Alta

---

### 3.3 Regras de Negócio

---

**RN-01 — Fonte exclusiva do banco de questões**
- **Descrição:** O banco de questões deve ser composto exclusivamente por provas oficiais disponibilizadas pelo portal do INEP. Nenhuma questão de origem não oficial pode ser inserida no sistema.
- **Requisitos relacionados:** RF-04, RF-05, RF-07

---

**RN-02 — Estrutura do simulado**
- **Descrição:** O simulado deve seguir a estrutura oficial do ENADE, contendo questões de Formação Geral e de Conhecimento Específico. A distribuição de questões deve ser proporcional à prova real do curso selecionado.
- **Requisitos relacionados:** RF-07, RF-08

---

**RN-03 — Cronômetro não pode ser pausado**
- **Descrição:** Uma vez iniciado, o cronômetro do simulado não pode ser pausado pelo estudante. O simulado é encerrado automaticamente ao término do tempo ou quando o estudante o finaliza manualmente.
- **Requisitos relacionados:** RF-08

---

**RN-04 — Gabarito disponível apenas após resposta**
- **Descrição:** O gabarito comentado de uma questão só pode ser visualizado após o estudante tê-la respondido (no modo banco de questões) ou após o encerramento do simulado. Durante a realização do simulado, o gabarito é inacessível.
- **Requisitos relacionados:** RF-06, RF-09

---

**RN-05 — Anonimização dos dados no painel da coordenação**
- **Descrição:** O painel da coordenação deve exibir exclusivamente dados agregados por turma. É vedada a exibição de desempenho individual nominalmente identificado, em conformidade com a LGPD.
- **Requisitos relacionados:** RF-11, RNF-03

---

**RN-06 — Publicação no fórum restrita a usuários autenticados**
- **Descrição:** Somente usuários com sessão autenticada podem publicar comentários no fórum. A leitura das discussões pode ser liberada para não autenticados, a critério da equipe.
- **Requisitos relacionados:** RF-12, RF-13

---

**RN-07 — Gamificação fora do escopo**
- **Descrição:** Funcionalidades de gamificação, como rankings, medalhas, pontuação acumulada ou recompensas virtuais, estão fora do escopo da versão 1.0 do sistema.
- **Requisitos relacionados:** N/A

---

## Apêndice A — Rastreabilidade de Requisitos

A tabela abaixo mapeia cada Requisito Funcional com seus Casos de Uso (UC) e Regras de Negócio (RN) associados.

| Requisito | Descrição Resumida | UC Associado | RN Associada |
|-----------|-------------------|--------------|--------------|
| RF-01 | Cadastro de usuário | UC-01 | — |
| RF-02 | Autenticação | UC-02 | — |
| RF-03 | Recuperação de senha | UC-02 | — |
| RF-04 | Visualizar questões | UC-03 | RN-01 |
| RF-05 | Filtrar questões | UC-03 | RN-01 |
| RF-06 | Gabarito comentado (banco) | UC-03 | RN-04 |
| RF-07 | Configurar simulado | UC-04 | RN-01, RN-02 |
| RF-08 | Realizar simulado cronometrado | UC-04 | RN-02, RN-03 |
| RF-09 | Resultado do simulado | UC-04 | RN-04 |
| RF-10 | Estatísticas individuais | UC-05 | — |
| RF-11 | Painel da coordenação | UC-06 | RN-05 |
| RF-12 | Publicar no fórum | UC-07 | RN-06 |
| RF-13 | Visualizar fórum | UC-07 | RN-06 |

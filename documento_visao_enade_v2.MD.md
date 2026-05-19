# P1 — Sistema de Preparação para o ENADE
**Disciplina:** Requisitos e Modelagem de Sistemas — UNIFOR  
**Grupo:** 1 | **Turma:** GR-R-261-T193-83  
**Alunos:** 4 | **João Pedro Carvalho, Daniel Gonçalves, Gabriel Catter, Tiago Pascoal.**


---

## Histórico de Versões

| Data | Versão | Descrição | Autor |
|------|--------|-----------|-------|
| 28/04/2026 | 1.0 | Criação inicial do documento de visão | Equipe de Desenvolvimento |
| 30/04/2026 | 2.0 | Atualização das seções 5, 8, 9, 10 | Equipe de Desenvolvimento |
| 19/05/2026 | 3.0 | Complementação com requisitos, backlog e diagramas UML | Equipe de Desenvolvimento |

---

# 1. Documento de Visão da Demanda (VD)

## 1.1 Objetivo

Definir a proposta de valor e o escopo do Sistema de Preparação para o ENADE, detalhando as necessidades dos estudantes de graduação, coordenações de curso e professores, com foco na democratização do acesso a materiais de estudo de qualidade e na melhoria do desempenho acadêmico.

## 1.2 Proposta de Valor

O sistema proporcionará uma plataforma web/mobile centralizada para estudo do ENADE, oferecendo banco de questões comentadas, simulados cronometrados e análise de desempenho. A solução permitirá que estudantes se preparem de forma organizada e realista, reduzindo a carência de materiais específicos e fornecendo feedback imediato sobre seu progresso. Para coordenações e professores, o sistema fornecerá dados para acompanhamento pedagógico.

## 1.3 Descrição da Demanda

O sistema apoiará estudantes de graduação no preparo para o Exame Nacional de Desempenho dos Estudantes (ENADE), oferecendo questões organizadas por ano, curso e área de conhecimento. Permitirá a realização de simulados cronometrados com gabaritos comentados, fórum de discussão para aprendizado colaborativo e visualização de estatísticas de desempenho individuais e por área. Todo o acesso será protegido por cadastro e autenticação segura.

## 1.4 Partes Interessadas (Stakeholders)

| Nome | Papel | Responsabilidades | Representante |
|------|-------|-------------------|---------------|
| Estudante | Usuário final | Utilizar a plataforma para estudo e simulados | — |
| Coordenação de Curso | Stakeholder | Acompanhar desempenho dos estudantes, validar aderência curricular | Coordenador do Curso |
| Professor | Stakeholder | Apoiar pedagogicamente na validação de questões e conteúdo | Prof. ENADE |
| Equipe de TI | Desenvolvimento | Documentar requisitos, modelar e prototipar o sistema | Equipe do Projeto |

## 1.5 Personas

### Persona 1 — Estudante de Graduação

| Atributo | Descrição |
|----------|-----------|
| **Descrição** | Aluno de graduação que realizará o ENADE como componente curricular obrigatório. |
| **Objetivo** | Ter acesso a materiais de estudo organizados, praticar com simulados realistas e entender seus erros por meio de comentários detalhados. |
| **Dores** | Dificuldade em encontrar materiais organizados por curso; falta de feedback imediato; sensação de despreparo por não conhecer o formato real do exame. |
| **Perfil Tecnológico** | Intermediário. Utiliza smartphone e computador com frequência; familiaridade com Moodle e aplicativos de estudo. |
| **Frequência de Uso** | Alta — acesso diário ou pelo menos 3x/semana nos meses que antecedem o exame. |
| **Frase Representativa** | *"Quero saber exatamente onde estou errando e por quê, para focar meu estudo no que realmente importa."* |

### Persona 2 — Coordenador de Curso

| Atributo | Descrição |
|----------|-----------|
| **Descrição** | Responsável pela gestão acadêmica do curso de graduação. |
| **Objetivo** | Acompanhar indicadores de preparação dos alunos, identificar áreas com maior dificuldade e propor ações de melhoria. |
| **Dores** | Falta de visibilidade sobre o desempenho dos alunos antes do exame; ausência de dados agregados por turma para embasar decisões pedagógicas. |
| **Perfil Tecnológico** | Intermediário. Utiliza ferramentas de gestão acadêmica e planilhas; prefere relatórios visuais e sintéticos. |
| **Frequência de Uso** | Média — acesso semanal/mensal para consulta de relatórios, com maior intensidade no período pré-exame. |
| **Frase Representativa** | *"Preciso identificar quais conteúdos meus alunos estão errando mais para orientar melhor as revisões antes do ENADE."* |

## 1.6 Necessidades e Funcionalidades

> **Nota:** O conteúdo do banco de questões será baseado em provas anteriores do ENADE, disponibilizadas pelo portal do INEP.

### Necessidade 1 — Acesso a banco de questões organizado

**F1.1 Organização de questões**
- **Descrição:** Permite visualizar questões organizadas por ano, curso, área de conhecimento e componente (Formação Geral ou Conhecimento Específico).
- **Status:** Incluída | **Atores:** Estudante | **Frequência:** Alta | **Valor:** Alto

### Necessidade 2 — Realização de simulados cronometrados

**F2.1 Sistema de simulado**
- **Descrição:** Permite realizar simulados com tempo cronometrado, simulando as condições reais do exame.
- **Status:** Incluída | **Atores:** Estudante | **Frequência:** Alta | **Valor:** Alto

### Necessidade 3 — Compreensão dos conceitos e erros

**F3.1 Gabarito comentado**
- **Descrição:** Exibe explicações detalhadas para cada resposta de questão, justificando o gabarito.
- **Status:** Incluída | **Atores:** Estudante | **Frequência:** Alta | **Valor:** Alto

### Necessidade 4 — Acompanhamento de desempenho

**F4.1 Estatísticas e gráficos**
- **Descrição:** Gera análise de desempenho individual por área de conhecimento com visualizações gráficas.
- **Status:** Incluída | **Atores:** Estudante | **Frequência:** Média | **Valor:** Alto

**F4.2 Painel da coordenação**
- **Descrição:** Permite que coordenadores de curso visualizem relatórios de desempenho agregado por turma.
- **Status:** Incluída | **Atores:** Coordenação de Curso | **Frequência:** Média | **Valor:** Médio

### Necessidade 5 — Aprendizado colaborativo

**F5.1 Fórum de discussão**
- **Descrição:** Espaço para interação entre usuários em cada questão, promovendo debate e aprendizado.
- **Status:** Incluída | **Atores:** Estudante | **Frequência:** Média | **Valor:** Médio

### Necessidade 6 — Segurança, desempenho e conformidade

**F6.1 Autenticação de usuários**
- **Descrição:** Garante que apenas usuários cadastrados acessem a plataforma, oferecendo login seguro.
- **Status:** Incluída | **Atores:** Estudante, Coordenação de Curso | **Frequência:** Sempre | **Valor:** Alto

**F6.2 Disponibilidade do sistema**
- **Descrição:** A plataforma deve estar disponível 24/7, com tolerância a falhas em horários não comerciais.
- **Status:** Incluída | **Atores:** Todos | **Frequência:** Sempre | **Valor:** Alto

**F6.3 Conformidade com INEP**
- **Descrição:** As questões utilizadas devem ter seu conteúdo baseado em provas oficiais do INEP, com as devidas referências.
- **Status:** Incluída | **Atores:** Equipe de TI, Professores | **Frequência:** Sempre | **Valor:** Alto

## 1.7 Arquitetura da Demanda

O sistema será concebido como uma plataforma web/mobile, composta pelos seguintes módulos:

- **Banco de Questões** — armazenamento e recuperação de questões organizadas por ano, curso e área
- **Simulados Cronometrados** — motor de realização de provas com controle de tempo
- **Gabaritos Comentados** — exibição de explicações após resposta ou encerramento de simulado
- **Estatísticas de Desempenho** — geração de gráficos e relatórios individuais e por turma
- **Fórum de Discussão** — espaço colaborativo vinculado a cada questão
- **Gestão de Usuários** — cadastro, autenticação e controle de perfis

A arquitetura de software seguirá o modelo **cliente-servidor**, com interfaces prototipadas para navegadores e dispositivos móveis. O banco de dados armazenará questões, perfis de usuário e histórico de desempenho.

---

# 2. Elicitação de Requisitos

## 2.1 Metodologia de Elicitação

Para identificar as necessidades reais dos usuários e stakeholders do sistema, foram utilizadas três técnicas complementares:

- **Entrevistas semiestruturadas** com estudantes de graduação (amostra: 4 entrevistados)
- **Questionário online** aplicado via Google Forms
- **Análise de documentos:** provas anteriores do ENADE (portal INEP) e diretrizes curriculares do MEC

## 2.2 Roteiro de Entrevista

O roteiro a seguir foi utilizado nas entrevistas com estudantes de graduação:

| # | Pergunta |
|---|----------|
| 1 | Você já utilizou alguma plataforma digital para se preparar para o ENADE? Se sim, qual foi sua experiência? |
| 2 | Quais são suas maiores dificuldades ao buscar material de estudo para o ENADE? |
| 3 | Você prefere estudar com questões organizadas por área/tema ou por ano de prova? Por quê? |
| 4 | Com que frequência você realizaria simulados completos antes do exame? |
| 5 | O que você considera indispensável em um gabarito comentado para realmente aprender com os erros? |
| 6 | Você participaria de fóruns de discussão sobre questões do ENADE em uma plataforma integrada? |
| 7 | Como você gostaria de visualizar seu desempenho ao longo do tempo (gráficos, relatórios, resumos)? |
| 8 | Você teria interesse em comparar seu desempenho com a média dos colegas do seu curso? |
| 9 | Qual dispositivo você usaria com mais frequência para acessar a plataforma (desktop, tablet, smartphone)? |
| 10 | O que poderia fazer você abandonar ou deixar de usar a plataforma? |

## 2.3 Resultados das Entrevistas

Foram entrevistados 4 estudantes de graduação de cursos distintos (Engenharia de Computação, Direito, Administração e Enfermagem).

| Tema | Achado Principal | Frequência |
|------|-----------------|------------|
| Materiais de estudo | 100% relataram dificuldade em encontrar questões organizadas por curso/área de forma gratuita. | 4/4 |
| Feedback sobre erros | Todos desejam gabaritos com explicação detalhada, não apenas indicação da resposta correta. | 4/4 |
| Simulados | 75% fariam simulados completos pelo menos 1x por semana no mês anterior ao exame. | 3/4 |
| Dispositivo preferido | Smartphone para acesso rápido; desktop para simulados completos. | 3/4 |
| Fórum de discussão | 50% demonstraram interesse moderado; 50% prefeririam apenas o gabarito comentado. | 2/4 |
| Visualização de desempenho | 100% querem ver evolução por área de conhecimento ao longo do tempo. | 4/4 |
| Comparativo com colegas | 75% gostariam de ver média do curso, não ranking individual. | 3/4 |

## 2.4 Necessidades Identificadas

| ID | Necessidade | Origem | Prioridade |
|----|-------------|--------|------------|
| NE-01 | Acesso a banco de questões organizado por ano, curso e área. | Entrevista + Análise Documental | Alta |
| NE-02 | Realização de simulados com cronômetro e condições reais. | Entrevista | Alta |
| NE-03 | Gabarito comentado com justificativa detalhada. | Entrevista | Alta |
| NE-04 | Visualização de desempenho individual com gráficos evolutivos. | Entrevista + Questionário | Alta |
| NE-05 | Fórum de discussão por questão. | Entrevista | Média |
| NE-06 | Painel da coordenação com dados agregados por turma. | Entrevista com Coordenação | Média |
| NE-07 | Autenticação segura de usuários (cadastro/login). | Análise de Segurança | Alta |
| NE-08 | Disponibilidade 24/7 da plataforma. | Análise Técnica | Alta |

---

# 3. Especificação de Requisitos

## 3.1 Requisitos Funcionais (RF)

| ID | Descrição | Prioridade | Ator(es) |
|----|-----------|------------|----------|
| RF-01 | O sistema deve permitir que o estudante visualize questões do ENADE filtradas por ano, curso, área de conhecimento e componente (Formação Geral / Conhecimento Específico). | Alta | Estudante |
| RF-02 | O sistema deve permitir a realização de simulados cronometrados com quantidade de questões e tempo configuráveis pelo estudante. | Alta | Estudante |
| RF-03 | O sistema deve exibir o gabarito comentado após a conclusão de cada simulado ou ao responder uma questão avulsa. | Alta | Estudante |
| RF-04 | O sistema deve gerar relatório de desempenho individual com gráficos por área de conhecimento e evolução temporal. | Alta | Estudante |
| RF-05 | O sistema deve disponibilizar um fórum de discussão vinculado a cada questão, permitindo que estudantes comentem e interajam. | Média | Estudante |
| RF-06 | O sistema deve disponibilizar ao coordenador de curso um painel com relatórios de desempenho agregado por turma. | Média | Coordenação |
| RF-07 | O sistema deve permitir o cadastro de novos usuários com confirmação de e-mail. | Alta | Todos |
| RF-08 | O sistema deve autenticar usuários por login e senha, com suporte a recuperação de senha. | Alta | Todos |
| RF-09 | O sistema deve registrar o histórico de simulados realizados pelo estudante, incluindo data, pontuação e tempo utilizado. | Alta | Estudante |
| RF-10 | O sistema deve notificar o estudante ao atingir metas de desempenho configuradas previamente. | Baixa | Estudante |
| RF-11 | O sistema deve permitir que o professor visualize e valide questões inseridas no banco, sinalizando as que necessitam de revisão. | Média | Professor |
| RF-12 | O sistema deve associar cada questão às referências da prova oficial do INEP da qual foi extraída. | Alta | Equipe TI / Prof. |

## 3.2 Requisitos Não Funcionais (RNF)

| ID | Categoria | Descrição | Critério de Aceitação |
|----|-----------|-----------|----------------------|
| RNF-01 | Disponibilidade | A plataforma deve estar disponível 24 horas por dia, 7 dias por semana. | Uptime ≥ 99,5% mensal; janela de manutenção programada entre 02h–04h. |
| RNF-02 | Desempenho | O carregamento de uma questão ou página de resultado não deve exceder 3 segundos em conexão de 10 Mbps. | Tempo de resposta p95 < 3s medido em testes de carga com 500 usuários simultâneos. |
| RNF-03 | Segurança | As senhas devem ser armazenadas com hash criptográfico (bcrypt ou Argon2). | Não deve existir senha em texto puro no banco de dados ou logs. |
| RNF-04 | Conformidade (LGPD) | O sistema deve coletar e tratar somente dados pessoais estritamente necessários e disponibilizar a opção de exclusão de conta. | Funcionalidade de exclusão de conta validada; Política de Privacidade disponível na plataforma. |
| RNF-05 | Usabilidade | A interface deve ser responsiva e utilizável em smartphones, tablets e desktops. | Aprovado em testes em Chrome/Firefox mobile e desktop sem quebra de layout. |
| RNF-06 | Manutenibilidade | O código-fonte deve seguir padrões documentados e possuir cobertura de testes unitários ≥ 70%. | Relatório de cobertura gerado na pipeline de CI/CD. |
| RNF-07 | Acessibilidade | A plataforma deve atender ao nível AA das Diretrizes WCAG 2.1. | Validação com ferramenta automatizada (axe ou similar) sem erros críticos. |
| RNF-08 | Conformidade (INEP) | Todo o conteúdo do banco de questões deve ser rastreável à prova oficial do INEP de origem. | 100% das questões com campo "fonte" preenchido (ano, edição, número da questão). |

## 3.3 Regras de Negócio (RN)

| ID | Descrição |
|----|-----------|
| RN-01 | Somente usuários autenticados podem acessar o banco de questões, realizar simulados e visualizar relatórios de desempenho. |
| RN-02 | O tempo do simulado é contado de forma regressiva e não pode ser pausado após o início; ao atingir zero, o simulado é encerrado automaticamente e o gabarito é gerado. |
| RN-03 | Cada questão deve conter, obrigatoriamente: enunciado, 5 alternativas (A–E), gabarito oficial e referência à prova INEP de origem. |
| RN-04 | O gabarito comentado somente é exibido após o estudante ter respondido a questão ou após o encerramento do simulado. |
| RN-05 | O painel da coordenação exibe apenas dados agregados (sem identificação individual) dos estudantes matriculados no curso do coordenador. |
| RN-06 | O sistema não deve exibir o nome nem o CPF do estudante em nenhum relatório público ou painel de coordenação, em conformidade com a LGPD. |
| RN-07 | Uma questão somente é incluída no banco após ser validada por um professor ou membro da equipe responsável. |
| RN-08 | O estudante pode refazer um simulado anteriormente realizado, mas o novo resultado é registrado como uma nova tentativa, sem sobrescrever o histórico. |
| RN-09 | Funcionalidades de gamificação (rankings, medalhas, pontuação competitiva) estão fora do escopo da versão 1.0 do sistema. |
| RN-10 | O sistema deve utilizar exclusivamente questões de provas oficiais do ENADE disponibilizadas publicamente pelo portal do INEP. |

---

# 4. Backlog Priorizado

O backlog está organizado pela técnica **MoSCoW** (Must Have, Should Have, Could Have, Won't Have na v1.0) e agrupado por épicos.

## 4.1 Épico 1 — Gestão de Usuários

| ID | User Story | Critério de Aceitação (Resumido) | Prioridade | Sprint |
|----|-----------|----------------------------------|------------|--------|
| US-01 | Como estudante, quero me cadastrar na plataforma informando nome, e-mail e senha, para ter acesso ao sistema. | E-mail de confirmação enviado; login liberado após confirmação. | Must Have | 1 |
| US-02 | Como usuário, quero fazer login com e-mail e senha para acessar minhas informações. | Login redireciona para dashboard; senha incorreta exibe mensagem de erro. | Must Have | 1 |
| US-03 | Como usuário, quero recuperar minha senha por e-mail caso a esqueça. | Link de redefinição enviado; nova senha aceita com sucesso. | Must Have | 1 |
| US-04 | Como usuário (LGPD), quero solicitar a exclusão da minha conta e de todos os meus dados. | Dados removidos em até 30 dias; confirmação enviada por e-mail. | Must Have | 2 |

## 4.2 Épico 2 — Banco de Questões

| ID | User Story | Critério de Aceitação (Resumido) | Prioridade | Sprint |
|----|-----------|----------------------------------|------------|--------|
| US-05 | Como estudante, quero buscar e filtrar questões por ano, curso e área de conhecimento para estudar de forma direcionada. | Filtros funcionais; questões carregam em menos de 3s. | Must Have | 2 |
| US-06 | Como estudante, quero visualizar o enunciado e as alternativas de uma questão de forma clara. | Layout responsivo; imagens e fórmulas exibidas corretamente. | Must Have | 2 |
| US-07 | Como professor, quero validar uma questão antes de ela ser publicada no banco. | Status da questão muda para "Publicada" após validação do professor. | Should Have | 3 |

## 4.3 Épico 3 — Simulados

| ID | User Story | Critério de Aceitação (Resumido) | Prioridade | Sprint |
|----|-----------|----------------------------------|------------|--------|
| US-08 | Como estudante, quero iniciar um simulado cronometrado com número de questões configurável. | Cronômetro iniciado; questões aleatorizadas; encerramento automático ao fim do tempo. | Must Have | 2 |
| US-09 | Como estudante, quero visualizar o resultado e o gabarito comentado ao finalizar o simulado. | Pontuação exibida; comentário exibido para cada questão respondida. | Must Have | 2 |
| US-10 | Como estudante, quero ver meu histórico de simulados realizados com data, pontuação e tempo. | Lista cronológica exibida no dashboard do estudante. | Should Have | 3 |

## 4.4 Épico 4 — Desempenho e Relatórios

| ID | User Story | Critério de Aceitação (Resumido) | Prioridade | Sprint |
|----|-----------|----------------------------------|------------|--------|
| US-11 | Como estudante, quero visualizar gráficos de meu desempenho por área de conhecimento. | Gráfico de barras/radar com percentual de acerto por área. | Must Have | 3 |
| US-12 | Como estudante, quero acompanhar minha evolução ao longo do tempo. | Gráfico de linha com desempenho médio por simulado realizado. | Should Have | 3 |
| US-13 | Como coordenador, quero visualizar o desempenho médio agregado dos alunos do meu curso. | Painel com média por área; sem dados individuais identificáveis. | Should Have | 4 |

## 4.5 Épico 5 — Interação e Colaboração

| ID | User Story | Critério de Aceitação (Resumido) | Prioridade | Sprint |
|----|-----------|----------------------------------|------------|--------|
| US-14 | Como estudante, quero comentar em questões e ver os comentários de outros estudantes. | Comentário publicado e exibido; moderação habilitada. | Could Have | 4 |
| US-15 | Como estudante, quero responder a um comentário existente em uma questão. | Resposta aninhada exibida corretamente abaixo do comentário original. | Could Have | 4 |

## 4.6 Resumo MoSCoW

| Classificação | Descrição | User Stories |
|---------------|-----------|-------------|
| **Must Have** | Funcionalidades essenciais sem as quais o sistema não entrega valor mínimo. | US-01 a US-09, US-11 |
| **Should Have** | Importantes para a experiência completa, mas não bloqueantes para o lançamento. | US-10, US-12, US-13 |
| **Could Have** | Desejáveis; adicionadas se houver capacidade disponível na sprint. | US-14, US-15 |
| **Won't Have (v1.0)** | Fora do escopo da primeira versão: gamificação, rankings, integração SSO institucional. | — |

---

# 5. Diagramas UML

> **Nota:** Os diagramas gráficos foram produzidos no Draw.io e estão disponíveis no repositório GitHub do projeto (pasta `/diagramas/`).

## 5.1 Diagrama de Casos de Uso

### Atores

- **Estudante** — usuário principal; acessa questões, realiza simulados, visualiza desempenho e participa do fórum.
- **Coordenador de Curso** — acessa painel agregado de desempenho da turma.
- **Professor** — valida questões do banco antes da publicação.
- **Administrador** — gerencia usuários e configurações do sistema (herda ações de todos os perfis).

### Casos de Uso

| ID UC | Nome | Ator Principal | Pré-condição | Pós-condição |
|-------|------|----------------|--------------|--------------|
| UC-01 | Cadastrar-se na plataforma | Estudante / Coordenador | Usuário não cadastrado | Conta criada; e-mail de confirmação enviado |
| UC-02 | Realizar Login | Todos | Usuário cadastrado | Sessão iniciada |
| UC-03 | Filtrar e visualizar questões | Estudante | Autenticado | Lista de questões exibida |
| UC-04 | Realizar simulado cronometrado | Estudante | Autenticado | Resultado e gabarito comentado gerados |
| UC-05 | Visualizar gabarito comentado | Estudante | Simulado concluído ou questão respondida | Comentário exibido por alternativa |
| UC-06 | Visualizar desempenho individual | Estudante | Ao menos 1 simulado realizado | Gráficos e métricas exibidos |
| UC-07 | Participar do fórum de questão | Estudante | Autenticado | Comentário publicado |
| UC-08 | Visualizar painel da coordenação | Coordenador | Autenticado com perfil Coordenador | Relatório agregado exibido |
| UC-09 | Validar questão | Professor | Autenticado com perfil Professor | Status da questão alterado para "Publicada" |
| UC-10 | Recuperar senha | Todos | Usuário cadastrado | Nova senha definida via link enviado por e-mail |

### Relacionamentos entre Casos de Uso

- UC-04 **inclui** UC-05 (gabarito comentado é gerado ao finalizar o simulado)
- UC-03 **estende** UC-04 (o estudante pode filtrar questões antes de iniciar um simulado)
- UC-02 **é pré-condição** para UC-03, UC-04, UC-06, UC-07, UC-08 e UC-09

## 5.2 Diagrama de Classes

### Classes do Domínio

#### Classe `Usuario` *(abstrata)*
| Atributos | Métodos |
|-----------|---------|
| `id: UUID` | `autenticar()` |
| `nome: String` | `recuperarSenha()` |
| `email: String` | `excluirConta()` |
| `senha: String (hash)` | |
| `tipo: Enum {Estudante, Coordenador, Professor}` | |
| `dataCadastro: Date` | |

#### Classe `Estudante` *(herda de Usuario)*
| Atributos | Métodos |
|-----------|---------|
| `curso: String` | `realizarSimulado()` |
| `periodo: Integer` | `visualizarDesempenho()` |
| | `comentarQuestao()` |

**Relacionamentos:** realiza `Simulado` (0..*), possui `Desempenho` (0..*), publica `Comentario` (0..*)

#### Classe `Coordenador` *(herda de Usuario)*
| Atributos | Métodos |
|-----------|---------|
| `codigoCurso: String` | `visualizarPainelTurma()` |

**Relacionamentos:** acessa `RelatorioTurma` (0..*)

#### Classe `Professor` *(herda de Usuario)*
| Atributos | Métodos |
|-----------|---------|
| `departamento: String` | `validarQuestao()` |

**Relacionamentos:** valida `Questao` (0..*)

#### Classe `Questao`
| Atributos | Métodos |
|-----------|---------|
| `id: UUID` | `exibirGabarito()` |
| `enunciado: Text` | `filtrar(ano, curso, area)` |
| `alternativas: List<String>` | |
| `gabarito: Char` | |
| `comentario: Text` | |
| `ano: Integer` | |
| `curso: String` | |
| `area: String` | |
| `componente: Enum {FG, CE}` | |
| `fonteINEP: String` | |
| `status: Enum {Pendente, Publicada}` | |

**Relacionamentos:** pertence a `Simulado` (0..*), possui `Comentario` (0..*)

#### Classe `Simulado`
| Atributos | Métodos |
|-----------|---------|
| `id: UUID` | `iniciar()` |
| `dataHora: DateTime` | `encerrar()` |
| `tempoLimite: Integer` | `calcularPontuacao()` |
| `tempoUtilizado: Integer` | |
| `pontuacao: Float` | |
| `status: Enum {Em andamento, Finalizado}` | |

**Relacionamentos:** pertence a `Estudante` (1), contém `Questao` (1..*), gera `Desempenho` (1)

#### Classe `Desempenho`
| Atributos | Métodos |
|-----------|---------|
| `id: UUID` | `calcularMetrica()` |
| `areaConhecimento: String` | `gerarGrafico()` |
| `percentualAcerto: Float` | |
| `totalQuestoes: Integer` | |
| `questoesCorretas: Integer` | |
| `data: Date` | |

**Relacionamentos:** pertence a `Estudante` (1), vinculado a `Simulado` (1)

#### Classe `Comentario`
| Atributos | Métodos |
|-----------|---------|
| `id: UUID` | `publicar()` |
| `texto: Text` | `excluir()` |
| `dataHora: DateTime` | |
| `autor: Estudante` | |

**Relacionamentos:** pertence a `Questao` (1), pode ter respostas `Comentario` (0..*)

#### Classe `RelatorioTurma`
| Atributos | Métodos |
|-----------|---------|
| `id: UUID` | `gerarRelatorio()` |
| `codigoCurso: String` | `exportar()` |
| `periodoRef: String` | |
| `mediaGeralArea: Map<String, Float>` | |

**Relacionamentos:** visualizado por `Coordenador` (1)

## 5.3 Diagrama de Sequência — UC-04: Realizar Simulado Cronometrado

**Atores/Objetos envolvidos:** Estudante, Interface Web, ControladorSimulado, BancoQuestoes, Simulado, DesempenhoService

| # | De | Para | Mensagem / Ação |
|---|----|------|----------------|
| 1 | Estudante | Interface Web | Seleciona filtros e clica em "Iniciar Simulado" |
| 2 | Interface Web | ControladorSimulado | `criarSimulado(filtros, tempo)` |
| 3 | ControladorSimulado | BancoQuestoes | `buscarQuestoes(filtros, quantidade)` |
| 4 | BancoQuestoes | ControladorSimulado | retorna `List<Questao>` |
| 5 | ControladorSimulado | Simulado | `new Simulado(questoes, tempoLimite)` |
| 6 | Simulado | Interface Web | retorna `simuladoId` + questões |
| 7 | Interface Web | Estudante | Exibe questões + cronômetro regressivo |
| 8 | Estudante | Interface Web | Responde questões (alternativas A–E) |
| 9 | Interface Web | ControladorSimulado | `registrarResposta(simuladoId, questaoId, alternativa)` |
| 10 | ControladorSimulado | Simulado | `adicionarResposta()` |
| 11 | Estudante / Timer | Interface Web | Clica "Finalizar" ou tempo esgotado |
| 12 | Interface Web | ControladorSimulado | `encerrarSimulado(simuladoId)` |
| 13 | ControladorSimulado | Simulado | `calcularPontuacao()` |
| 14 | ControladorSimulado | DesempenhoService | `registrarDesempenho(estudanteId, simulado)` |
| 15 | ControladorSimulado | Interface Web | retorna resultado + gabarito comentado |
| 16 | Interface Web | Estudante | Exibe pontuação, acertos por área e comentários |

---

# 6. Restrições e Premissas do Sistema

## 6.1 Restrições

- O sistema é um projeto conceitual — não haverá implementação de código funcional nesta fase (fase de elicitação e modelagem).
- O banco de questões será composto exclusivamente por provas oficiais do INEP, respeitando as referências legais de uso público.
- Funcionalidades de gamificação (rankings, medalhas, pontuação competitiva) estão fora do escopo da versão 1.0.
- A plataforma deve estar em conformidade com a **Lei Geral de Proteção de Dados (LGPD — Lei nº 13.709/2018)** no tratamento de dados pessoais dos usuários.
- A documentação técnica deve seguir os padrões **IEEE 830** (SRS) e notação **UML** para os diagramas.

## 6.2 Premissas

- As provas do ENADE disponibilizadas pelo portal do INEP são de acesso público e podem ser utilizadas para fins educacionais.
- Os estudantes possuem acesso à internet e a dispositivos compatíveis (computador ou smartphone) para utilizar a plataforma.
- As coordenações de curso demonstrarão interesse em adotar a plataforma como ferramenta de acompanhamento pedagógico.
- Os requisitos levantados refletem as necessidades reais dos estudantes, validadas por meio de entrevistas e questionários.

## 6.3 Dependências

- **Portal do INEP** (www.inep.gov.br): fonte primária das provas e gabaritos oficiais do ENADE.
- **Ferramentas de modelagem UML** (Draw.io / Lucidchart / Astah): elaboração dos diagramas do projeto.
- **Ferramentas de prototipação** (Figma / Adobe XD / Balsamiq): criação dos wireframes (fora do escopo desta entrega).

---

# 7. Glossário

| Termo / Sigla | Definição |
|---------------|-----------|
| **ENADE** | Exame Nacional de Desempenho dos Estudantes. Avalia o rendimento dos alunos dos cursos de graduação em relação aos conteúdos programáticos, habilidades e competências. É componente curricular obrigatório. |
| **INEP** | Instituto Nacional de Estudos e Pesquisas Educacionais Anísio Teixeira. Autarquia federal responsável pela realização do ENADE e pela disponibilização das provas anteriores em seu portal oficial. |
| **SRS** | Software Requirements Specification. Documento padronizado pela norma IEEE 830 que descreve de forma completa os requisitos funcionais e não funcionais de um sistema. |
| **UML** | Unified Modeling Language. Notação padrão para modelagem de sistemas de software, incluindo diagramas de Caso de Uso, Classes, Sequência e Atividades. |
| **Stakeholder** | Parte interessada no sistema. Qualquer pessoa, grupo ou organização que possui interesse direto ou indireto no projeto ou é afetada pelo sistema desenvolvido. |
| **Simulado Cronometrado** | Prova de prática composta por questões do ENADE, realizada com controle de tempo, simulando as condições reais do exame oficial. |
| **Gabarito Comentado** | Resposta correta acompanhada de explicação detalhada, justificando por que a alternativa correta está certa e, quando possível, por que as demais estão erradas. |
| **Formação Geral (FG)** | Componente do ENADE que avalia competências gerais dos estudantes, independentemente do curso. |
| **Conhecimento Específico (CE)** | Componente do ENADE que avalia os conteúdos e competências técnicas relativos à área de formação do estudante. |
| **Elicitação** | Processo de levantamento de requisitos junto aos stakeholders, utilizando técnicas como entrevistas, questionários e análise documental. |
| **Backlog** | Lista priorizada de funcionalidades, melhorias e correções que devem ser desenvolvidas no sistema. |
| **LGPD** | Lei Geral de Proteção de Dados (Lei nº 13.709/2018). Legislação brasileira que regulamenta o tratamento de dados pessoais. |
| **Requisito Funcional** | Descrição de uma função ou comportamento específico que o sistema deve executar — define *O QUE* o sistema faz. |
| **Requisito Não Funcional** | Restrição ou qualidade que o sistema deve atender, sem descrever uma função específica — define *COMO* o sistema se comporta. |
| **Persona** | Personagem fictício criado para representar um grupo de usuários com características, objetivos e comportamentos similares. |
| **User Story** | Descrição informal de uma funcionalidade do sistema escrita da perspectiva do usuário final, no formato: *"Como \<ator\>, quero \<ação\> para \<benefício\>."* |
| **MoSCoW** | Técnica de priorização: Must Have (obrigatório), Should Have (importante), Could Have (desejável), Won't Have (fora do escopo). |
| **Wireframe** | Esboço estrutural de uma interface de usuário, representando o layout e a disposição dos elementos sem detalhes visuais finais. |

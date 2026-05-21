# Visão da Demanda (VD)

**Documento de Visão — Sistema de Preparação para o ENADE**

 

## Histórico de Versões

 

| **Data** | **Versão** | **Descrição** | **Autor** |
| --- | --- | --- | --- |
| 28/04/2026 | 1.0 | Criação inicial do documento de visão para o Sistema de Preparação para o ENADE | Equipe de Desenvolvimento |
| 30/04/26 | 2.0 | Atualização das seções 5, 8, 9, 10 | Equipe de Desenvolvimento |
|  |  |  |  |

 

## 1. Objetivo

Definir a proposta de valor e o escopo do Sistema de Preparação para o ENADE, detalhando as necessidades dos estudantes de graduação, coordenações de curso e professores, com foco na democratização do acesso a materiais de estudo de qualidade e na melhoria do desempenho acadêmico.

 

## 2. Proposta de Valor

O sistema proporcionará uma plataforma web/mobile centralizada para estudo do ENADE, oferencendo banco de questões comentadas, simulados cronometrados e análise de desempenho. A solução permitirá que estudantes se preparem de forma organizada e realista, reduzindo a carência de materiais específicos e fornecendo feedback imediato sobre seu progresso. Para coordenações e professores, o sistema fornecerá dados para acompanhamento pedagógico.

 

## 3. Descrição da Demanda

O sistema apoiará estudantes de graduação no preparo para o Exame Nacional de Desempenho dos Estudantes, oferecendo questões organizadas por ano, curso e área de conhecimento. Permitirá a realização de simulados cronometrados com gabaritos comentados, fórum de discussão para aprendizado colaborativo e visualização de estatísticas de desempenho individuais e por área. Todo o acesso será protegido por cadastro e autenticação segura.

 

## 4. Partes Interessadas

 

| **Nome** | **Papel** | **Responsabilidades** | **Representante** |
| --- | --- | --- | --- |
| Estudante | Usuário final | Utilizar a plataforma para estudo e simulados | - |
| Coordenação de Curso | Stakeholder | Acompanhar desempenho dos estudantes, validar aderência curricular | Coordenador do Curso |
| Professor | Stakeholder | Apoiar pedagogicamente na validação de questões e conteúdo | Prof. ENADE |
| Equipe de TI | Desenvolvimento | Documentar requisitos, modelar e prototipar o sistema | Equipe do Projeto |

 

## 5. Personas

### 5.1. Estudante de Graduação

- **Descrição:** Aluno de graduação que realizará o ENADE como componente curricular obrigatório.

- **Objetivo:** Ter acesso a materiais de estudo organizados, praticar com simulados realistas e entender seus erros através de comentários detalhados.

- **Dores / Frustrações:** Dificuldade em encontrar materiais organizados por curso; falta de feedback imediato sobre erros; sensação de despreparo por não conhecer o formato real do exame.

- **Perfil Tecnológico:** Intermediário. Utiliza smartphone e computador com frequência, tem familiaridade com plataformas educacionais como Moodle e aplicativos de estudo.

- **Frequência de Uso Esperada:** Alta — acesso diário ou pelo menos 3x por semana nos meses que antecedem o exame.

- **Frase Representativa:** "Quero saber exatamente onde estou errando e por quê, para focar meu estudo no que realmente importa."

 

### 5.2. Coordenador de Curso

- **Descrição:** Responsável pela gestão acadêmica do curso de graduação.

- **Objetivo:** Acompanhar indicadores de preparação dos alunos, identificar áreas com maior dificuldade e propor ações de melhoria.

- **Dores / Frustrações:** Falta de visibilidade sobre o desempenho dos alunos antes do exame; ausência de dados agregados por turma para embasar decisões pedagógicas.

- **Perfil Tecnológico:** Intermediário. Utiliza ferramentas de gestão acadêmica e planilhas; prefere relatórios visuais e sintéticos.

- **Frequência de Uso Esperada:** Média — acesso semanal ou mensal para consulta de relatórios, com maior intensidade no período pré-exame.

- **Frase Representativa:** "Preciso identificar quais conteúdos meus alunos estão errando mais para orientar melhor as revisões antes do ENADE."

 

## 6. Necessidades e Funcionalidades

### Necessidade 1: Acesso a banco de questões organizado

**Nota:** O conteúdo do banco de questões será baseado em provas anteriores do ENADE, disponibilizadas pelo portal do INEP.

 

#### F1.1 Organização de questões

- **Descrição:** Permite visualizar questões organizadas por ano, curso, área de conhecimento e componente (formação geral ou conhecimento específico).

- **Incluída**

- **Atores:** Estudante

- **Frequência:** Alta

- **Valor:** Alto

 

### Necessidade 2: Realização de simulados cronometrados

#### F2.1 Sistema de simulado

- **Descrição:** Permite realizar simulados com tempo cronometrado, simulando as condições reais do exame.

- **Incluída**

- **Atores:** Estudante

- **Frequência:** Alta

- **Valor:** Alto

 

### Necessidade 3: Compreensão dos conceitos e erros

#### F3.1 Gabarito comentado

- **Descrição:** Exibe explicações detalhadas para cada resposta de questão, justificando o gabarito.

- **Incluída**

- **Atores:** Estudante

- **Frequência:** Alta

- **Valor:** Alto

 

### Necessidade 4: Acompanhamento de desempenho

#### F4.1 Estatísticas e gráficos

- **Descrição:** Gera análise de desempenho individual por área de conhecimento com visualizações gráficas.

- **Incluída**

- **Atores:** Estudante

- **Frequência:** Média

- **Valor:** Alto

 

#### F4.2 Painel da coordenação

- **Descrição:** Permite que coordenadores de curso visualizem relatórios de desempenho agregado por turma.

- **Incluída**

- **Atores:** Coordenação de Curso

- **Frequência:** Média (por ciclo de prova)

- **Valor:** Médio

 

### Necessidade 5: Aprendizado colaborativo

#### F5.1 Fórum de discussão

- **Descrição:** Espaço para interação entre usuários em cada questão, promovendo debate e aprendizado.

- **Incluída**

- **Atores:** Estudante

- **Frequência:** Média

- **Valor:** Médio

 

### Necessidade 6: Segurança, desempenho e conformidade

#### F6.1 Autenticação de usuários

- **Descrição:** Garante que apenas usuários cadastrados acessem a plataforma, oferecendo login seguro.

- **Incluída**

- **Atores:** Estudante, Coordenação de Curso

- **Frequência:** Sempre

- **Valor:** Alto

 

 

#### F6.2 Disponibilidade do sistema

- **Descrição:** A plataforma deve estar disponível 24/7, com tolerância a falhas em horários não comerciais.

- **Incluída**

- **Atores:** Todos

- **Frequência:** Sempre

- **Valor:** Alto

 

#### F6.3 Conformidade com INEP

- **Descrição:** As questões utilizadas devem ter seu conteúdo baseado em provas oficiais do INEP, com as devidas referências.

- **Incluída**

- **Atores:** Equipe de TI, Professores

- **Frequência:** Sempre

- **Valor:** Alto

 

## 7. Arquitetura da Demanda

O sistema será concebido como uma plataforma web/mobile, composta por módulos de: Banco de Questões, Simulados Cronometrados, Gabaritos Comentados, Estatísticas de Desempenho, Fórum de Discussão e Gestão de Usuários. Utilizará banco de dados para armazenamento de questões, perfis de usuário e histórico de desempenho. A arquitetura de software seguirá o modelo cliente-servidor, com interfaces prototipadas para navegadores e dispositivos móveis.

 

### Diagrama de Caso de Uso

## 8. Restrições do Sistema

As seguintes restrições se aplicam ao escopo e desenvolvimento do sistema:

- O sistema é um projeto conceitual — não haverá implementação de código funcional nesta fase.

- O banco de questões será composto exclusivamente por provas oficiais do INEP, respeitando as referências legais de uso público.

- Funcionalidades de gamificação (rankings, medalhas, etc.) estão fora do escopo da versão 1.0.

- A plataforma deve estar em conformidade com a Lei Geral de Proteção de Dados (LGPD — Lei n° 13.709/2018) no tratamento de dados pessoais dos usuários.

- A documentação técnica deve seguir os padrões IEEE 830 (SRS) e notação UML para os diagramas.

 

## 9. Premissas e Dependências

### 9.1 Premissas

- As provas do ENADE disponibilizadas pelo portal do INEP são de acesso público e podem ser utilizadas para fins educacionais.

- Os estudantes possuem acesso à internet e a dispositivos compatíveis (computador ou smartphone) para utilizar a plataforma.

- As coordenações de curso demonstrarão interesse em adotar a plataforma como ferramenta de acompanhamento pedagógico.

- Os requisitos levantados refletem as necessidades reais dos estudantes, validadas por meio de entrevistas e questionários.

### 9.2 Dependências

- Portal do INEP (www.inep.gov.br): fonte primária das provas e gabaritos oficiais do ENADE.

- Ferramentas de modelagem UML (Lucidchart, Draw.io ou Astah) para elaboração dos diagramas do projeto.

- Ferramentas de prototipação de interface (Figma, Adobe XD ou Balsamiq) para criação dos wireframes.

 

## 10. Glossário

Esta seção define os principais termos e siglas utilizados ao longo do documento.

| **Termo / Sigla** | **Definição** |
| --- | --- |
| **ENADE** | Exame Nacional de Desempenho dos Estudantes. Avalia o rendimento dos alunos dos cursos de graduação em relação aos conteúdos programáticos, habilidades e competências. É componente curricular obrigatório. |
| **INEP** | Instituto Nacional de Estudos e Pesquisas Educacionais Anísio Teixeira. Autarquia federal responsável pela realização do ENADE e pela disponibilização das provas anteriores em seu portal oficial. |
| **SRS** | Software Requirements Specification (Especificação de Requisitos de Software). Documento padronizado pela norma IEEE 830 que descreve de forma completa os requisitos funcionais e não funcionais de um sistema. |
| **UML** | Unified Modeling Language (Linguagem de Modelagem Unificada). Notação padrão para modelagem de sistemas de software, incluindo diagramas de Caso de Uso, Classes, Sequência e Atividades. |
| **Stakeholder** | Parte interessada no sistema. Qualquer pessoa, grupo ou organização que possui interesse direto ou indireto no projeto ou é afetada pelo sistema desenvolvido. |
| **Simulado Cronometrado** | Prova de prática composta por questões do ENADE, realizada com controle de tempo, simulando as condições reais do exame oficial para fins de treino e avaliação do estudante. |
| **Gabarito Comentado** | Resposta correta de uma questão acompanhada de explicação detalhada, justificando o motivo pelo qual a alternativa correta está certa e, quando possível, por que as demais estão erradas. |
| **Formação Geral** | Componente do ENADE que avalia competências gerais dos estudantes, independentemente do curso, como leitura, interpretação de texto, raciocínio lógico e questões interdisciplinares. |
| **Conhecimento Específico** | Componente do ENADE que avalia os conteúdos e competências técnicas relativos à área de formação do estudante (ex.: Engenharia, Direito, Medicina, etc.). |
| **Elicitação** | Processo de levantamento de requisitos junto aos stakeholders, utilizando técnicas como entrevistas, questionários, observação e workshops, com o objetivo de identificar as necessidades do sistema. |
| **Backlog** | Lista priorizada de funcionalidades, melhorias e correções que devem ser desenvolvidas no sistema. No contexto ágil, representa o conjunto de itens de trabalho ordenados por valor e urgência. |
| **LGPD** | Lei Geral de Proteção de Dados (Lei n° 13.709/2018). Legislação brasileira que regulamenta o tratamento de dados pessoais por pessoas físicas e jurídicas, garantindo direitos aos titulares dos dados. |
| **Requisito Funcional** | Descrição de uma função ou comportamento específico que o sistema deve executar. Define O QUE o sistema faz (ex.: o sistema deve permitir que o estudante realize um simulado cronometrado). |
| **Requisito Não Funcional** | Restrição ou qualidade que o sistema deve atender, mas que não descreve uma função específica. Define COMO o sistema deve se comportar (ex.: tempo de resposta, disponibilidade, segurança). |
| **Persona** | Personagem fictício criado para representar um grupo de usuários com características, objetivos e comportamentos similares. Utilizado na engenharia de requisitos para guiar decisões de design e funcionalidade. |
| **Wireframe** | Esboço estrutural de uma interface de usuário, representando o layout e a disposição dos elementos sem detalhes visuais finais. Utilizado para validar fluxos e funcionalidades antes da implementação. |

# Definicão De Histórias de Usuário

---

# 1. Relembrem o Problema do Projeto

Registrem novamente, de maneira breve:

**Problema que o projeto procura resolver:**

> ________________________________________________

**Objetivo do produto:**

> ________________________________________________

**Quem será beneficiado pelo produto?**

> ________________________________________________

Evitem começar pensando em telas ou funcionalidades. Comecem pelo **problema e pelas pessoas envolvidas**.

---

# 2. Identifiquem os Stakeholders

Stakeholders são as partes interessadas que podem afetar ou ser afetadas pelo sistema.

Identifiquem pelo menos **5 stakeholders**.

| Stakeholder | Relação com o sistema | O que precisa do sistema? |
|---|---|---|
| | | |
| | | |
| | | |

Pergunta para orientar:

> **Quem possui necessidades que nosso produto precisa atender?**

---

# 3. Identifiquem Necessidades

Para cada stakeholder, registrem pelo menos uma necessidade.

Exemplo:

**Stakeholder:** recepcionista de uma clínica.

**Necessidade:**

> Precisa saber rapidamente quais horários estão disponíveis para atendimento.

Ainda não escrevam a solução técnica.

Evitem:

> “Precisa de uma tela com calendário.”

Prefiram:

> “Precisa saber quais horários estão disponíveis.”

---

# 4. Transformem as Necessidades em Requisitos

Agora analisem as necessidades identificadas e escrevam requisitos para o produto.

O grupo deverá produzir pelo menos:

- **10 requisitos funcionais;**
- **6 requisitos não funcionais;**
- **2 requisitos de domínio/negócio.**

## Requisitos Funcionais

Descrevem aquilo que o sistema deverá fazer.

Exemplo:

> RF01 — O sistema deve permitir consultar os horários disponíveis de cada veterinário.

> RF02 — O sistema deve permitir registrar uma consulta.

## Requisitos Não Funcionais

Representam restrições ou propriedades de qualidade.

Sempre que possível, escrevam de maneira mensurável.

Exemplo:

> RNF01 — A consulta dos horários disponíveis deve ser apresentada em até 2 segundos.

> RNF02 — Apenas usuários autenticados poderão acessar dados dos clientes.

## Requisitos de Domínio

Representam regras impostas pelo contexto no qual o sistema será utilizado.

Exemplo:

> RD01 — Um veterinário somente poderá receber consultas de espécies para as quais esteja habilitado.

---

# 5. Classifiquem os Requisitos

Construam uma tabela:

| ID | Requisito | Tipo | Stakeholder relacionado |
|---|---|---|---|
| RF01 | | Funcional | |
| RF02 | | Funcional | |
| RNF01 | | Não funcional | |
| RD01 | | Domínio | |

Durante essa etapa, discutam:

> **Qual necessidade deu origem a esse requisito?**

Se o grupo não conseguir responder, talvez o requisito não esteja suficientemente justificado.

---

# 6. Transformem Requisitos Funcionais em Histórias de Usuário

Agora selecionem os **requisitos funcionais** e os expressem como histórias de usuário.

Utilizem:

> **Como [stakeholder], quero [objetivo], para [valor/benefício].**

### Exemplo

Requisito:

> RF01 — O sistema deve permitir consultar os horários disponíveis de cada veterinário.

História:

> **Como recepcionista, quero visualizar os horários disponíveis de um veterinário para encontrar um horário adequado para a consulta.**

Façam isso para pelo menos **6 histórias de usuário**.

| Requisito | História de usuário |
|---|---|
| RF01 | Como..., quero..., para... |
| RF02 | |
| RF03 | |

---

# 7. Analisem a Qualidade das Histórias

Para cada história, respondam:

1. Existe um stakeholder claramente identificado?
2. Está claro o que ele pretende realizar?
3. Está claro o valor ou benefício?
4. A história parece pequena o suficiente para ser trabalhada?
5. Conseguimos imaginar como verificar se ela foi satisfeita?

Se alguma resposta for **não**, revisem a história.

### Exemplo problemático

> Como usuário, quero gerenciar todo o sistema para facilitar meu trabalho.

Problemas:

- “usuário” é genérico;
- objetivo excessivamente grande;
- benefício vago.

### Melhor

> Como gerente, quero consultar o total de atendimentos realizados no mês para acompanhar o desempenho da clínica.

---

# 8. Definam Critérios de Aceitação

Para cada uma das histórias criadas, definam entre **pelo menos 5 critérios de aceitação**.

### Exemplo

História:

> Como recepcionista, quero visualizar os horários disponíveis de um veterinário para encontrar um horário adequado para a consulta.

Critérios:

- deve ser possível selecionar um veterinário;
- deve ser possível selecionar uma data;
- horários já ocupados não devem aparecer como disponíveis;
- caso não existam horários, o sistema deverá informar o usuário.

Pergunta central:

> **Como saberemos que essa história foi atendida?**

---

# 9. Relacionem RNFs e Regras de Domínio às Histórias

Nem todo requisito precisa virar uma história de usuário.

Por exemplo:

### História

> Como recepcionista, quero consultar os horários disponíveis de um veterinário para encontrar um horário para a consulta.

### RNF relacionado

> A lista deverá ser apresentada em até 2 segundos.

### Regra de domínio relacionada

> Apenas veterinários habilitados para a espécie do animal poderão ser apresentados.

Construam uma tabela:

| História | RF | RNF relacionado | Regra de domínio |
|---|---|---|---|
| Consultar horários | RF01 | RNF01 | RD01 |
| | | | |

A ideia é perceber que:

> **História de usuário não representa toda a especificação.**

Ela expressa principalmente uma necessidade ou funcionalidade; restrições e regras complementam essa história.

---

# 10. Levem as Histórias para o Trello

Agora atualizem o **Product Backlog** do projeto.

Cada história deverá virar um card.

## Título

Utilizem um título curto:

> Consultar horários disponíveis

## Descrição

Coloquem a história completa:

> Como recepcionista, quero visualizar os horários disponíveis de um veterinário para encontrar um horário adequado para a consulta.

Também podem registrar:

**Requisito relacionado:** RF01

**Regras relacionadas:** RD01

**RNFs relacionados:** RNF01

## Checklist — Critérios de Aceitação

- [ ] permitir selecionar veterinário;
- [ ] permitir selecionar data;
- [ ] apresentar apenas horários livres;
- [ ] informar quando não houver horários disponíveis.

Quando a história entrar em uma Sprint, o grupo poderá adicionar uma segunda checklist:

## Checklist — Tarefas

- [ ] revisar regras;
- [ ] definir informações necessárias;
- [ ] criar protótipo;
- [ ] validar com o grupo.

---

# 11. Priorizem as Histórias

Organizem o Product Backlog considerando:

- valor para o stakeholder;
- importância para resolver o problema principal;
- dependências;
- risco;
- incerteza.

Selecionem as **3 histórias mais prioritárias** e justifiquem:

> **Por que essa história deve ser tratada antes das demais?**

---

# 12. Revisão Cruzada

Troquem o projeto com outro grupo.

O outro grupo deverá selecionar **duas histórias** e analisar:

- O stakeholder está claro?
- A necessidade está clara?
- O valor está claro?
- Existem ambiguidades?
- Os critérios de aceitação são verificáveis?
- Existe algum RNF ou regra de domínio que parece estar faltando?

O grupo avaliador deve fornecer **uma sugestão de melhoria** para cada história.

Depois, o grupo original decide se modifica ou não seus cards.

---

# Entregável

Cada grupo deverá entregar:

1. definição breve do problema e objetivo;
2. lista de stakeholders;
3. necessidades identificadas;
4. pelo menos 6 requisitos funcionais;
5. pelo menos 3 requisitos não funcionais;
6. pelo menos 2 requisitos de domínio;
7. pelo menos 6 histórias de usuário;
8. critérios de aceitação para as 3 histórias prioritárias;
9. associação entre histórias, RNFs e regras de domínio;
10. Product Backlog atualizado no Trello;
11. link do quadro Trello.

---

# Estrutura Conceitual da Atividade

Ao final, os alunos deverão conseguir enxergar:

> **Stakeholder**  
> ↓  
> **Necessidade**  
> ↓  
> **Requisito**  
> ↓  
> **História de usuário**  
> ↓  
> **Critérios de aceitação**

Enquanto:

> **Requisitos não funcionais + regras de domínio**

complementam e restringem as histórias.

---

# Fechamento

Respondam:

> **Se já temos histórias de usuário, por que ainda precisamos estudar Engenharia de Requisitos?**

A conclusão esperada é que histórias são uma forma de registrar e comunicar determinadas necessidades, mas identificar stakeholders, descobrir necessidades, lidar com restrições, regras de negócio, qualidade, ambiguidades e validação continua sendo trabalho de Engenharia de Requisitos.

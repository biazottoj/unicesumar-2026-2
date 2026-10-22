# Atividade — Diagrama de Classes do Projeto da Disciplina

**Valor:** 0,5 ponto

## Objetivo

Construir um **Diagrama de Classes UML** relacionado ao mesmo projeto que o grupo vem desenvolvendo ao longo da disciplina e organizando no Trello.

O objetivo da atividade é transformar parte dos requisitos e histórias de usuário já levantados pelo grupo em uma representação da estrutura do sistema.

---

## Instruções

Cada grupo deverá analisar o projeto e identificar as principais classes necessárias para representar o domínio da aplicação.

O diagrama deverá conter, no mínimo:

- **10 classes**;
- atributos relevantes em cada classe;
- métodos coerentes com as responsabilidades das classes;
- relacionamentos entre as classes;
- multiplicidades nos relacionamentos;
- pelo menos **um caso de generalização/herança**, caso exista uma relação conceitualmente adequada no projeto;
- pelo menos **1 classe associativa**.

---

## 1. Revisem o projeto

Antes de iniciar o diagrama, retomem:

- problema que o projeto pretende resolver;
- stakeholders identificados;
- requisitos funcionais;
- histórias de usuário registradas no Product Backlog;
- principais regras de negócio.

Utilizem essas informações para descobrir quais conceitos do domínio devem aparecer como classes.

---

## 2. Identifiquem as classes

Procurem os principais elementos do domínio do projeto.

Por exemplo, em um sistema de clínica veterinária, poderíamos identificar:

- Cliente;
- Animal;
- Veterinário;
- Consulta;
- Especialidade;
- Pagamento.

Evitem transformar automaticamente telas, botões ou operações em classes.

Por exemplo:

**Evitar:**

- TelaCadastro;
- BotaoSalvar;
- FormularioConsulta.

Prefiram representar entidades e conceitos importantes do domínio.

---

## 3. Definam os atributos

Cada classe deverá conter os atributos necessários para representar suas informações principais.

### Exemplo

**Animal**

- idAnimal
- nome
- dataNascimento
- especie

Não é necessário incluir todos os possíveis atributos do sistema. Escolham aqueles que sejam relevantes para compreender o modelo.

---

## 4. Definam os métodos

Adicionem métodos relacionados às responsabilidades das classes.

### Exemplo

**Consulta**

- agendar()
- cancelar()
- reagendar()

Evitem métodos puramente relacionados à interface, como:

- clicarBotao()
- abrirTela()
- mostrarFormulario()

Os métodos devem representar comportamentos coerentes com as responsabilidades das classes.

---

## 5. Definam os relacionamentos

Analisem como as classes se relacionam.

Para cada relacionamento, indiquem corretamente a **multiplicidade**.

Também identifiquem:

- associações;
- generalização/herança, quando aplicável;
- classe associativa, quando necessária para representar um relacionamento que possua informações próprias.

---

## Entrega

O grupo deverá entregar **um arquivo PDF** contendo todos os elementos descritos acima.

O diagrama poderá ser construído utilizando uma ferramenta UML, como **Draw.io**, **Lucidchart**, ou outra ferramenta que permita representar corretamente a notação UML.

A entrega deverá ser realizada via **Google Forms** no link:

https://forms.gle/xKBa2vWShD8WmrZq8

### Datas de entrega

- **ADSIS2S-N-A — até 28/09**
- **ESOFT2S-N-B — até 27/09**

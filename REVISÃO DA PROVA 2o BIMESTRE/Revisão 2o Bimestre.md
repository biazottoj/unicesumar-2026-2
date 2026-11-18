# Lista de Revisão — UML: Casos de Uso, Classes e Sequência

**Disciplina:** Engenharia de Software  
**Modalidade:** questões teóricas e práticas  
**Conteúdos:** Diagrama de Casos de Uso, Diagrama de Classes e Diagrama de Sequência

## Orientações

Esta lista contém **24 questões**, organizadas em três partes. Nas questões discursivas, justifique as respostas usando os conceitos estudados. Nas questões práticas, desenhe os diagramas solicitados e identifique corretamente seus elementos. **Para os diagramas de sequência, utilize PlantUML.** Os demais podem ser feitos em PlantUML ou em uma ferramenta de modelagem UML.

**Editor online do PlantUML:** https://editor.plantuml.com/uml/  
**Referência de diagramas de sequência:** https://plantuml.com/sequence-diagram

Não é necessário desenvolver ou programar o sistema. Um **gabarito comentado, em arquivo separado**, acompanha esta lista para estudo posterior.

---

## Cenário de referência — SalaLivre

A universidade deseja construir o **SalaLivre**, um sistema de reserva de salas de estudo. Um **estudante** possui matrícula, nome e e-mail. Ele pode consultar as salas cadastradas, solicitar reservas e cancelar suas próprias reservas. Cada **sala** possui código, capacidade e localização. O sistema permite consultar a disponibilidade de uma sala para uma data e um intervalo de horário.

Uma **reserva** registra identificador, data/hora de início, data/hora de término e situação (`solicitada`, `confirmada` ou `cancelada`). Cada reserva pertence a **um estudante** e se refere a **uma sala**. Um estudante pode ter várias reservas, assim como uma sala pode aparecer em várias reservas em horários distintos. **Não podem existir duas reservas confirmadas sobrepostas para uma mesma sala.** Uma reserva só pode ser cancelada por seu próprio estudante e quando ainda estiver ativa. Após uma reserva ser confirmada, o estudante pode **opcionalmente** solicitar um comprovante por e-mail.

A universidade também organiza **grupos de estudo**, cada um com identificador, tema e descrição. Um estudante pode participar de vários grupos, e cada grupo pode reunir vários estudantes. Para cada vínculo entre um estudante e um grupo, o sistema registra a **participação**, com data de entrada e papel do estudante no grupo (`integrante` ou `organizador`). Para este exercício, considere que um estudante pode possuir **no máximo uma participação por grupo**.

Nos exercícios de sequência, considere ainda que o sistema pode ter uma **lista de espera** para um horário ocupado e um componente de **notificações** que envia avisos por e-mail.

> Use esse cenário como base quando a questão mencionar o SalaLivre. Outros cenários serão descritos integralmente no próprio enunciado.

---

# Parte I — Diagrama de Casos de Uso

### Questão 1 — Finalidade do diagrama (teórica)

Explique qual é a finalidade de um **Diagrama de Casos de Uso**. Diferencie **ator** e **caso de uso** e explique por que um botão ou uma tela, por si só, normalmente não representa um caso de uso.

### Questão 2 — Relacionamentos (teórica)

Compare os relacionamentos `<<include>>` e `<<extend>>`. Indique a finalidade de cada um, em que circunstâncias são utilizados e **para onde aponta a seta** de cada relacionamento.

### Questão 3 — Generalização (teórica)

Explique o significado de **generalização de atores** em um Diagrama de Casos de Uso. Crie um exemplo de ator genérico e dois atores especializados, mostrando quais interações eles herdam.

### Questão 4 — Limites do sistema (teórica)

Explique a função da **fronteira do sistema** no Diagrama de Casos de Uso. Um serviço externo de pagamento ou envio de e-mails deve aparecer como ator ou como caso de uso interno? Justifique conforme o limite escolhido para o sistema.

### Questão 5 — Identificação de casos de uso (prática)

Com base no **SalaLivre**, identifique **um ator principal** e **cinco casos de uso** que representem objetivos reais desse ator. Para cada caso de uso, escreva em uma frase o resultado esperado. Evite ações técnicas como “clicar em botão”, “criar tabela” ou “abrir formulário”.

### Questão 6 — Construção de diagrama (prática)

Considere a seguinte extensão do SalaLivre: **estudantes e docentes** são tipos de **membros da universidade**. Ambos podem **consultar salas** e **reservar salas**. Para efetuar uma reserva, o sistema **sempre verifica a disponibilidade**. Após reservar, o membro pode, **se desejar**, **solicitar um comprovante**.

Construa um **Diagrama de Casos de Uso UML** contendo:

- a fronteira do sistema;
- os três atores e sua generalização;
- os casos de uso mencionados;
- associações entre ator e caso de uso;
- **um `<<include>>`** e **um `<<extend>>`**, com sentido correto das setas.

### Questão 7 — Escolha do relacionamento (prática)

Classifique os relacionamentos a seguir como **associação**, **`<<include>>`**, **`<<extend>>`** ou **generalização**. Justifique cada resposta e, quando houver seta de dependência ou herança, explique seu sentido.

**a)** Para reservar uma sala, o sistema obrigatoriamente precisa verificar a disponibilidade.  
**b)** Depois de confirmar a reserva, o usuário pode optar por emitir um comprovante.  
**c)** `Docente` é um tipo específico de `MembroUniversidade`.  
**d)** O ator `Estudante` utiliza o caso de uso `Consultar salas`.

### Questão 8 — Análise de um diagrama (prática)

Uma equipe apresentou as seguintes relações em um Diagrama de Casos de Uso:

```text
Reservar sala ..> Verificar disponibilidade : <<extend>>
Emitir comprovante ..> Reservar sala : <<include>>
MembroUniversidade --|> Docente
```

Sabendo que **verificar disponibilidade é obrigatório**, **emitir comprovante é opcional** e **Docente é especializado de MembroUniversidade**, identifique **três problemas** e apresente as relações corretas.

---

# Parte II — Diagrama de Classes

### Questão 9 — Estrutura da classe (teórica)

Explique a diferença entre **classe**, **atributo** e **método**. Usando o SalaLivre, apresente um exemplo de classe com pelo menos dois atributos e um método coerente com sua responsabilidade.

### Questão 10 — Multiplicidades (teórica)

Explique o significado das multiplicidades `1`, `0..1`, `0..*` e `1..*` em associações UML. Em seguida, dê um exemplo de relação do domínio SalaLivre que utilize pelo menos duas delas.

### Questão 11 — Visibilidade (teórica)

Explique o significado dos símbolos UML `+`, `-`, `#` e `~` utilizados antes de atributos e métodos. Associe-os aos níveis de visibilidade correspondentes e explique como se relacionam ao **encapsulamento**.

### Questão 12 — Tipos de relacionamento (teórica)

Diferencie **associação**, **agregação**, **composição** e **generalização** em Diagramas de Classes. Explique também o que é uma **classe associativa** e quando ela pode ser necessária.

### Questão 13 — Identificação de classes (prática)

A partir do SalaLivre, selecione **três classes do domínio**. Para cada classe, indique:

- pelo menos **três atributos** relevantes, com tipos sugeridos;
- pelo menos **dois métodos** coerentes com suas responsabilidades;
- uma justificativa curta de por que é uma classe, e não apenas uma tela ou um botão.

### Questão 14 — Relacionamentos e multiplicidades (prática)

Represente e justifique as multiplicidades nos seguintes relacionamentos do SalaLivre:

**a)** `Estudante` e `Reserva`;  
**b)** `Sala` e `Reserva`;  
**c)** `Estudante` e `GrupoEstudo`.

Para o item **c**, explique por que as informações `dataEntrada` e `papel` não deveriam ser atributos permanentes de `Estudante` nem de `GrupoEstudo`.

### Questão 15 — Classe associativa (prática)

Modele o vínculo entre `Estudante` e `GrupoEstudo` utilizando a classe associativa **`Participacao`**. Inclua `dataEntrada` e `papel` e identifique as multiplicidades. Explique qual fato do domínio essa classe representa.

> Considere um único vínculo entre cada par estudante–grupo, conforme o cenário. Você pode usar a notação UML de classe associativa ou uma classe intermediária ligada às duas entidades, desde que a semântica da associação fique clara.

### Questão 16 — Diagrama de Classes completo (prática)

Construa um Diagrama de Classes para a **parte de reservas** do SalaLivre, contendo as classes `Estudante`, `Sala` e `Reserva`.

Seu diagrama deverá conter:

- pelo menos **três atributos por classe**;
- pelo menos **um método por classe**;
- visibilidade UML nos atributos e nos métodos;
- relacionamentos e **multiplicidades corretas**;
- métodos que possam ser utilizados para **consultar disponibilidade**, **confirmar** e **cancelar** uma reserva.

Não invente uma herança apenas para preencher o diagrama: use somente relações coerentes com o cenário.

---

# Parte III — Diagrama de Sequência

### Questão 17 — Finalidade e tempo (teórica)

Explique o objetivo de um **Diagrama de Sequência**. O que é uma **lifeline**? Em qual direção o tempo progride? Diferencie a informação apresentada por esse diagrama daquela apresentada por um Diagrama de Classes.

### Questão 18 — Mensagens e retornos (teórica)

Explique, no contexto de um Diagrama de Sequência, a diferença entre **chamada de operação** e **mensagem de retorno**. Como geralmente são representadas? O que representa uma **barra de ativação**?

### Questão 19 — Fragmentos combinados (teórica)

Explique a finalidade de `alt`, `opt` e `loop`. Dê um exemplo concreto de utilização de cada um em um sistema de software e explique quando um bloco `alt` pode conter outro bloco `alt`.

### Questão 20 — Consistência entre diagramas (teórica)

Uma mensagem de um Diagrama de Sequência pode corresponder a um método de uma classe. Explique por que é importante manter essa consistência. A interface e o serviço que coordenam a interação precisam necessariamente aparecer como classes de domínio no Diagrama de Classes? Justifique.

### Questão 21 — Diagrama simples: consultar sala (prática)

Construa **em PlantUML** um Diagrama de Sequência para o seguinte cenário:

1. `Estudante` seleciona uma sala no `PortalReservas`.
2. O portal solicita os dados ao `CatalogoSalas`.
3. O catálogo consulta a `Sala`.
4. A sala retorna código, capacidade e localização.
5. O catálogo devolve os dados ao portal.
6. O portal apresenta as informações ao estudante.

**Inclua:** ator, participantes, chamadas e retornos. **Não é necessário usar `alt`, `opt` ou `loop`.**

### Questão 22 — Diagrama intermediário: reservar sala (prática)

Construa **em PlantUML** um Diagrama de Sequência para o seguinte cenário:

1. O `Estudante` solicita no `PortalReservas` a reserva de uma `Sala`, informando data e horário.
2. O portal encaminha a solicitação ao `ServicoReservas`.
3. O serviço consulta a disponibilidade da `Sala`, que responde se o horário está livre.
4. **Se estiver livre**, o serviço registra a `Reserva`, obtém uma confirmação e solicita ao portal que informe o sucesso.
5. **Se estiver ocupado**, o serviço solicita ao portal que informe a indisponibilidade.

**Inclua:** chamadas, retornos e **um `alt` com os dois caminhos**.

### Questão 23 — Diagrama elaborado: cancelar e avisar interessados (prática)

Construa **em PlantUML** um Diagrama de Sequência para o cenário a seguir:

1. Um `Estudante` solicita ao `PortalReservas` o cancelamento de uma reserva.
2. O portal encaminha a solicitação ao `ServicoReservas`.
3. O serviço consulta `Reserva` para verificar se o estudante é o responsável.
4. **Se não for o responsável**, a operação é negada e o portal exibe a mensagem apropriada.
5. **Se for o responsável**, o serviço verifica se a reserva está ativa.
6. **Se não estiver ativa**, o portal informa que não há reserva ativa a cancelar.
7. **Se estiver ativa**, o serviço cancela a `Reserva`, solicita à `Sala` que libere o horário e consulta a `ListaEspera`.
8. **Se houver interessados**, para **cada estudante da lista**, o `ServicoReservas` solicita ao `Notificador` o envio de um aviso e recebe a confirmação do envio.
9. **Opcionalmente**, se o estudante que cancelou solicitou comprovante, o serviço pede ao `Notificador` seu envio.
10. Quando o cancelamento for bem-sucedido, o portal apresenta a confirmação ao estudante.

**Inclua:** mensagens, retornos, **`alt` aninhados**, **`opt`** e **`loop`**. Mostre claramente os caminhos de erro e de sucesso.

### Questão 24 — Integração entre os diagramas (prática)

Considere a história de usuário do SalaLivre:

> **Como estudante, quero reservar uma sala em um horário livre para realizar minhas atividades de estudo.**

Descreva como essa história seria representada nos **três tipos de diagrama** estudados. Sua resposta deverá identificar:

**a)** no Diagrama de Casos de Uso, um ator e dois casos de uso relacionados;  
**b)** no Diagrama de Classes, as classes e operações essenciais ao cenário;  
**c)** no Diagrama de Sequência, os principais participantes, as chamadas e uma condição necessária.

Conclua explicando por que os três diagramas são **complementares**, e não três maneiras equivalentes de desenhar a mesma informação.

---

## Checklist de estudo

Ao terminar a lista, verifique se você consegue:

- [ ] Distinguir ator, caso de uso e fronteira do sistema.
- [ ] Utilizar `<<include>>`, `<<extend>>` e generalização corretamente.
- [ ] Identificar classes, atributos, métodos e responsabilidades.
- [ ] Interpretar visibilidade, multiplicidades e tipos de relacionamento.
- [ ] Reconhecer quando uma classe associativa é necessária.
- [ ] Transformar um cenário textual em mensagens ordenadas.
- [ ] Utilizar retornos, `alt`, `opt` e `loop` em PlantUML.
- [ ] Verificar a coerência entre Casos de Uso, Classes e Sequência.

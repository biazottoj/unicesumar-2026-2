# Sistema de Reservas de Hotel

## Cenário para Construção de Diagrama de Classes

Um hotel deseja desenvolver um sistema para gerenciar seus quartos, hóspedes, reservas, pagamentos e operações relacionadas à hospedagem.

O hotel possui diversos **quartos**. Cada quarto possui um número que o identifica, quantidade máxima de hóspedes, valor da diária e situação atual, indicando, por exemplo, se o quarto está disponível, ocupado ou em manutenção.

Cada quarto pertence a um determinado **tipo de quarto**, como *Standard*, *Luxo* ou *Suíte*. Um tipo de quarto pode estar associado a vários quartos e possui informações como nome, descrição e capacidade padrão.

Para utilizar os serviços do hotel, é necessário manter informações sobre os **hóspedes**. Para cada hóspede, o sistema registra dados como nome, CPF, telefone e e-mail.

Um hóspede pode realizar diversas **reservas** ao longo do tempo. Cada reserva, entretanto, pertence a apenas um hóspede e está associada a um quarto. Um mesmo quarto pode aparecer em diferentes reservas, desde que os períodos das reservas não entrem em conflito.

Para cada reserva, devem ser registradas informações como:

- código da reserva;
- data de entrada prevista;
- data de saída prevista;
- quantidade de hóspedes;
- data em que a reserva foi realizada;
- valor total;
- situação da reserva.

Uma reserva pode apresentar diferentes situações ao longo do seu ciclo de vida, como *pendente*, *confirmada*, *cancelada*, *em andamento* ou *finalizada*.

O valor da reserva é calculado considerando a quantidade de diárias e o valor da diária do quarto. Em determinados períodos considerados de **alta temporada**, uma taxa adicional pode ser aplicada ao valor da hospedagem.

Uma reserva pode possuir um ou mais **pagamentos**. Cada pagamento registra informações como valor, data, situação e identificação da transação. Os pagamentos pertencem exclusivamente à reserva à qual estão associados.

O sistema aceita diferentes formas de pagamento. Atualmente, um pagamento pode ser realizado por **PIX** ou por **cartão de crédito**.

Um pagamento via PIX possui informações específicas, como código da transação PIX e identificador do pagamento.

Um pagamento com cartão possui informações próprias, como bandeira do cartão, últimos quatro dígitos e código de autorização da transação.

Quando uma reserva já paga é cancelada e atende às regras estabelecidas pelo hotel, pode ser realizado um **reembolso**. O reembolso deve registrar o valor devolvido, a data em que ocorreu e sua situação. Um reembolso está relacionado ao pagamento que originou a devolução.

Além dos hóspedes, o sistema mantém informações sobre os **funcionários** do hotel. Todos os funcionários possuem informações como código funcional, nome, CPF e salário.

Existem diferentes tipos de funcionários.

Os **recepcionistas** são responsáveis pelas operações relacionadas à entrada e à saída dos hóspedes. Um recepcionista pode realizar diversos check-ins e check-outs ao longo do tempo.

Os **gerentes**, além de serem funcionários do hotel, possuem responsabilidades administrativas, como cadastrar e alterar quartos e acompanhar informações relacionadas à ocupação do hotel.

Quando o hóspede chega ao hotel, é realizado um **check-in** relacionado a uma reserva. O sistema registra a data e hora da entrada e o recepcionista responsável pelo atendimento. Uma reserva pode possuir no máximo um check-in.

Ao final da hospedagem, é realizado um **check-out**. O check-out registra a data e hora da saída, possíveis valores adicionais cobrados e o recepcionista responsável. Uma reserva pode possuir no máximo um check-out.

Portanto, o sistema deve permitir representar informações relacionadas a hóspedes, funcionários, quartos, tipos de quarto, reservas, pagamentos, reembolsos, check-ins e check-outs, bem como os relacionamentos existentes entre esses elementos.

---

## Regras de Negócio

Para construir o modelo, considere também as seguintes regras:

1. Um hóspede pode possuir nenhuma ou várias reservas.
2. Toda reserva pertence obrigatoriamente a um único hóspede.
3. Toda reserva está relacionada a um único quarto.
4. Um quarto pode participar de várias reservas ao longo do tempo.
5. Duas reservas confirmadas para o mesmo quarto não podem possuir períodos conflitantes.
6. Todo quarto pertence a um único tipo de quarto.
7. Um tipo de quarto pode estar associado a vários quartos.
8. Uma reserva pode não possuir pagamento ou possuir vários pagamentos.
9. Todo pagamento pertence a uma única reserva.
10. Um pagamento pode ser realizado por PIX ou cartão de crédito.
11. Um reembolso está relacionado a um pagamento.
12. Nem todo pagamento possui um reembolso.
13. Todo recepcionista é um funcionário.
14. Todo gerente é um funcionário.
15. Um funcionário não precisa necessariamente ser simultaneamente recepcionista e gerente.
16. Um check-in pertence a uma única reserva e é realizado por um recepcionista.
17. Uma reserva pode possuir no máximo um check-in.
18. Um check-out pertence a uma única reserva e é realizado por um recepcionista.
19. Uma reserva pode possuir no máximo um check-out.
20. Uma reserva somente pode possuir check-out depois da realização do check-in.

---

## Comportamentos Esperados

Além das informações armazenadas, algumas classes deverão possuir comportamentos relacionados às suas responsabilidades.

Por exemplo, o sistema precisa ser capaz de:

- calcular o valor de uma reserva;
- verificar se uma reserva ocorre durante a alta temporada;
- calcular uma eventual taxa de alta temporada;
- verificar a disponibilidade de um quarto em determinado período;
- confirmar uma reserva;
- cancelar uma reserva;
- registrar um pagamento;
- verificar se um pagamento foi confirmado;
- realizar um reembolso;
- registrar o check-in;
- registrar o check-out;
- calcular valores pendentes no momento do check-out.

Durante a construção do diagrama, esses comportamentos devem ser associados às classes que possuem a responsabilidade mais adequada para executá-los.

---

## Objetivo

A partir da descrição apresentada, construa um **Diagrama de Classes UML** para o Sistema de Reservas de Hotel.

O diagrama deve representar:

- classes;
- atributos relevantes;
- métodos principais;
- associações;
- multiplicidades;
- generalizações;
- possíveis relações de agregação ou composição, quando apropriadas.

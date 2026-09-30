# Exercícios de Orientação a Objetos

## Lista de Exercícios

1. Qual conceito da Orientação a Objetos representa um modelo utilizado para criar objetos?  
   a) Método  
   b) Classe  
   c) Atributo  
   d) Interface

2. Um objeto é:  
   a) Uma função independente  
   b) Uma instância de uma classe  
   c) Um tipo de variável primitiva  
   d) Um pacote Java

3. Qual alternativa representa melhor um **atributo**?  
   a) `calcularTotal()`  
   b) `nome`  
   c) `Cliente()`  
   d) `public`

4. Qual alternativa representa melhor um **método**?  
   a) `idade`  
   b) `saldo`  
   c) `depositar()`  
   d) `Cliente`

5. Em uma classe `Pessoa`, qual dos itens abaixo provavelmente seria um atributo?  
   a) `nome`  
   b) `cadastrar()`  
   c) `Pessoa()`  
   d) `main()`

6. Em uma classe `ContaBancaria`, qual dos itens abaixo provavelmente seria um método?  
   a) `saldo`  
   b) `numeroConta`  
   c) `depositar()`  
   d) `titular`

7. Qual conceito permite esconder os detalhes internos de um objeto e controlar o acesso aos seus dados?  
   a) Herança  
   b) Encapsulamento  
   c) Polimorfismo  
   d) Sobrecarga

8. Qual modificador normalmente é utilizado para impedir o acesso direto a um atributo fora da classe?  
   a) `public`  
   b) `private`  
   c) `static`  
   d) `final`

9. Métodos `get` são normalmente utilizados para:  
   a) Modificar atributos  
   b) Consultar valores de atributos  
   c) Criar objetos  
   d) Excluir classes

10. Métodos `set` são normalmente utilizados para:  
   a) Alterar valores de atributos  
   b) Criar novas classes  
   c) Destruir objetos  
   d) Criar herança

11. Qual conceito permite que uma classe reutilize características de outra classe?  
   a) Encapsulamento  
   b) Herança  
   c) Abstração  
   d) Sobrecarga

12. Se `Cachorro` herda de `Animal`, podemos afirmar que:  
   a) Animal é uma subclasse de Cachorro  
   b) Cachorro é uma subclasse de Animal  
   c) As classes não possuem relação  
   d) Animal é um método

13. Na relação `Carro` herda de `Veiculo`, qual é a superclasse?  
   a) Carro  
   b) Veiculo  
   c) Motor  
   d) Nenhuma

14. Qual relação abaixo representa adequadamente uma herança?  
   a) Cachorro é um Animal  
   b) Carro possui um Motor  
   c) Pessoa possui um CPF  
   d) Pedido possui Produtos

15. Qual das alternativas abaixo **não** representa uma boa relação de herança?  
   a) Professor é uma Pessoa  
   b) Cachorro é um Animal  
   c) Carro é um Motor  
   d) Gerente é um Funcionário

16. Qual conceito permite que objetos de diferentes classes respondam de formas diferentes à mesma operação?  
   a) Encapsulamento  
   b) Polimorfismo  
   c) Composição  
   d) Instanciação

17. `Animal` possui o método `emitirSom()`. `Cachorro` redefine esse método para latir. Qual conceito está sendo aplicado?  
   a) Sobrecarga  
   b) Sobrescrita  
   c) Encapsulamento  
   d) Composição

18. Quando uma subclasse fornece uma nova implementação para um método herdado, temos:  
   a) Sobrecarga  
   b) Sobrescrita  
   c) Abstração  
   d) Encapsulamento

19. Ter dois métodos chamados `calcular`, mas com parâmetros diferentes, representa:  
   a) Sobrescrita  
   b) Sobrecarga  
   c) Herança múltipla  
   d) Encapsulamento

20. Qual situação representa **sobrecarga de métodos**?  
   a) `somar(int a, int b)` e `somar(double a, double b)`  
   b) Uma classe herdar de outra  
   c) Um atributo ser privado  
   d) Uma classe possuir um objeto

21. Qual é a principal função de um construtor?  
   a) Destruir objetos  
   b) Inicializar objetos  
   c) Criar métodos abstratos  
   d) Criar interfaces

22. Qual método é executado normalmente no momento da criação de um objeto?  
   a) Getter  
   b) Setter  
   c) Construtor  
   d) Método abstrato

23. Em Java, o nome de um construtor deve ser:  
   a) Igual ao nome da classe  
   b) Sempre `constructor`  
   c) Igual ao nome do primeiro atributo  
   d) Sempre `main`

24. Uma classe pode possuir mais de um construtor?  
   a) Não  
   b) Sim, desde que tenham parâmetros diferentes  
   c) Sim, desde que todos sejam iguais  
   d) Apenas quando é abstrata

25. Criar um objeto a partir de uma classe é chamado de:  
   a) Encapsulamento  
   b) Instanciação  
   c) Sobrescrita  
   d) Generalização

26. Na instrução conceitual `Pessoa p = new Pessoa()`, `p` representa:  
   a) Uma classe  
   b) Uma referência para um objeto  
   c) Um método  
   d) Uma interface

27. Qual conceito busca representar somente as características importantes de uma entidade, ignorando detalhes desnecessários?  
   a) Abstração  
   b) Sobrecarga  
   c) Instanciação  
   d) Associação

28. Uma classe abstrata pode ser utilizada principalmente para:  
   a) Representar uma ideia geral que será especializada por outras classes  
   b) Criar apenas variáveis  
   c) Impedir completamente a herança  
   d) Substituir todos os objetos

29. Uma classe abstrata normalmente:  
   a) Pode ser instanciada diretamente  
   b) Não pode ser instanciada diretamente  
   c) Não pode possuir métodos  
   d) Não pode possuir atributos

30. Um método abstrato possui como característica principal:  
   a) Não possuir implementação na classe abstrata  
   b) Ser sempre privado  
   c) Não possuir nome  
   d) Ser obrigatoriamente estático

31. Qual elemento é utilizado para definir um conjunto de comportamentos que uma classe deve implementar?  
   a) Interface  
   b) Atributo  
   c) Construtor  
   d) Pacote

32. Quando uma classe implementa uma interface, ela assume o compromisso de:  
   a) Implementar os métodos exigidos pela interface  
   b) Transformar todos os atributos em públicos  
   c) Não possuir construtores  
   d) Não utilizar herança

33. Considere a interface `Pagamento` com o método `pagar()`. Qual classe faria sentido implementar essa interface?  
   a) CartaoCredito  
   b) Pessoa  
   c) Endereco  
   d) DataNascimento

34. Qual alternativa representa melhor uma interface?  
   a) Um contrato de comportamentos  
   b) Um objeto já criado  
   c) Uma variável primitiva  
   d) Um construtor especial

35. Qual conceito está sendo utilizado quando uma classe possui um objeto de outra classe?  
   a) Associação  
   b) Sobrescrita  
   c) Sobrecarga  
   d) Instanciação

36. `Pessoa` possui um `Endereco`. Essa relação pode ser classificada genericamente como:  
   a) Associação  
   b) Herança  
   c) Sobrescrita  
   d) Polimorfismo

37. Qual expressão representa melhor uma relação de composição?  
   a) É um  
   b) Possui um  
   c) Executa um  
   d) Herda um

38. Qual relação representa melhor composição?  
   a) Casa possui Quartos  
   b) Cachorro é Animal  
   c) Professor é Pessoa  
   d) Carro é Veículo

39. Qual relação representa melhor uma relação do tipo **“é um”**?  
   a) Carro é um Veículo  
   b) Carro possui um Motor  
   c) Pessoa possui um Endereço  
   d) Pedido possui Produtos

40. Qual relação representa melhor uma relação do tipo **“possui um”**?  
   a) Aluno é Pessoa  
   b) Cachorro é Animal  
   c) Carro possui Motor  
   d) Gerente é Funcionário

41. Uma classe `Produto` possui `nome`, `preco` e `estoque`. Esses elementos são:  
   a) Métodos  
   b) Atributos  
   c) Construtores  
   d) Interfaces

42. Uma classe `Produto` possui `calcularDesconto()` e `atualizarEstoque()`. Esses elementos são:  
   a) Atributos  
   b) Métodos  
   c) Classes abstratas  
   d) Objetos

43. Considere `Aluno`, `Professor`, `Disciplina` e `String`. Qual alternativa provavelmente representa uma classe do domínio de um sistema escolar?  
   a) `Aluno`  
   b) `public`  
   c) `if`  
   d) `return`

44. Em um sistema de biblioteca, qual alternativa provavelmente representa uma classe?  
   a) Livro  
   b) Emprestar  
   c) Público  
   d) Repetir

45. Em um sistema de vendas, qual alternativa provavelmente representa um método da classe `Pedido`?  
   a) `numeroPedido`  
   b) `dataPedido`  
   c) `calcularTotal()`  
   d) `cliente`

46. Em um sistema bancário, qual alternativa provavelmente representa um atributo da classe `Conta`?  
   a) `sacar()`  
   b) `depositar()`  
   c) `saldo`  
   d) `transferir()`

47. Qual princípio é aplicado ao declarar `saldo` como privado e permitir sua alteração apenas através de métodos específicos?  
   a) Polimorfismo  
   b) Encapsulamento  
   c) Herança  
   d) Sobrecarga

48. `Funcionario` possui o método `calcularSalario()`. `Gerente` e `Vendedor` implementam cálculos diferentes para esse método. Qual conceito está sendo explorado?  
   a) Polimorfismo  
   b) Encapsulamento  
   c) Composição  
   d) Instanciação

49. Observe os elementos abaixo: `nome`, `idade`, `andar()` e `Pessoa`. Qual deles representa uma classe?  
   a) `nome`  
   b) `idade`  
   c) `andar()`  
   d) `Pessoa`

50. Observe os elementos abaixo de uma classe `Carro`: `modelo`, `ano`, `acelerar()` e `frear()`. Qual alternativa está correta?  
   a) Todos são atributos  
   b) Todos são métodos  
   c) `modelo` e `ano` são atributos; `acelerar()` e `frear()` são métodos  
   d) `modelo` e `ano` são métodos; `acelerar()` e `frear()` são atributos

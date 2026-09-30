# Lista de Exercícios — Orientação a Objetos

## Conteúdos abordados
- Classe
- Objeto
- Método
- Atributo
- Herança
- Abstração

---

## Exercícios

1. Em um sistema acadêmico, `Aluno` possui `nome`, `matricula` e `curso`. Esses elementos representam:
   a) Métodos  
   b) Atributos  
   c) Objetos  
   d) Classes derivadas

2. Em uma classe `ContaBancaria`, as operações `depositar()` e `sacar()` representam:
   a) Atributos  
   b) Métodos  
   c) Objetos  
   d) Classes

3. Qual alternativa apresenta apenas elementos que poderiam ser atributos de uma classe `Produto`?
   a) `nome`, `preco`, `estoque`  
   b) `calcularPreco()`, `nome`, `vender()`  
   c) `Produto`, `estoque`, `atualizar()`  
   d) `comprar()`, `vender()`, `listar()`

4. Em um sistema de biblioteca, qual alternativa representa melhor uma possível classe?
   a) `Livro`  
   b) `emprestar()`  
   c) `titulo`  
   d) `quantidadePaginas`

5. Uma classe pode ser entendida como:
   a) Uma definição que descreve características e comportamentos de objetos  
   b) Um valor armazenado em uma variável  
   c) Um objeto específico criado durante a execução  
   d) Uma operação realizada por um objeto

6. Dois objetos criados a partir da mesma classe:
   a) Devem possuir exatamente os mesmos valores em seus atributos  
   b) Podem possuir valores diferentes para seus atributos  
   c) Não podem executar os mesmos métodos  
   d) Representam obrigatoriamente classes diferentes

7. Em uma aplicação, `cliente1` e `cliente2` possuem nome e CPF diferentes, mas seguem a mesma estrutura. A explicação mais adequada é:
   a) São métodos da mesma classe  
   b) São objetos da mesma classe  
   c) São atributos de classes diferentes  
   d) São duas subclasses

8. Qual alternativa descreve melhor um objeto?
   a) Uma definição genérica utilizada para representar um tipo de entidade  
   b) Uma instância concreta de uma classe  
   c) Uma operação realizada dentro de uma classe  
   d) Uma característica comum entre subclasses

9. Considere uma classe `Carro` com `modelo`, `ano` e `velocidadeAtual`. Esses elementos descrevem:
   a) O estado dos objetos da classe  
   b) A hierarquia da classe  
   c) Os comportamentos da classe  
   d) As subclasses disponíveis

10. Na classe `Carro`, `acelerar()` e `frear()` indicam:
    a) Características armazenadas  
    b) Comportamentos possíveis dos objetos  
    c) Classes relacionadas  
    d) Objetos criados

11. Em uma classe `Pessoa`, qual alternativa apresenta corretamente um atributo e um método, nessa ordem?
    a) `nome` e `falar()`  
    b) `andar()` e `idade`  
    c) `Pessoa` e `nome`  
    d) `falar()` e `andar()`

12. Considere a classe `Livro` com os elementos `titulo`, `autor`, `emprestar()` e `devolver()`. Qual alternativa está correta?
    a) Todos são atributos  
    b) Todos são métodos  
    c) `titulo` e `autor` são atributos; os demais são métodos  
    d) `titulo` e `autor` são métodos; os demais são atributos

13. Em um sistema de vendas, qual alternativa representa melhor um método da classe `Pedido`?
    a) `data`  
    b) `valorTotal`  
    c) `calcularTotal()`  
    d) `numero`

14. Em um sistema escolar, qual alternativa representa melhor um atributo da classe `Aluno`?
    a) `matricula`  
    b) `realizarProva()`  
    c) `consultarNota()`  
    d) `entregarTrabalho()`

15. Em uma classe `Lampada`, `ligada` armazena se a lâmpada está acesa ou apagada. Esse elemento é:
    a) Um método  
    b) Um atributo  
    c) Uma classe  
    d) Uma abstração

16. Em uma classe `Lampada`, `ligar()` altera o estado da lâmpada. Esse elemento é:
    a) Um objeto  
    b) Um atributo  
    c) Um método  
    d) Uma superclasse

17. Qual alternativa apresenta melhor uma classe e um objeto dessa classe?
    a) `Carro` e um Honda Civic específico  
    b) `acelerar()` e `velocidade`  
    c) `nome` e `Pessoa`  
    d) `Animal` e `emitirSom()`

18. Em um sistema de restaurantes, `Mesa` é usada para representar todas as mesas do estabelecimento. `mesa12` representa uma mesa específica. Nesse caso:
    a) Ambos são classes  
    b) `Mesa` é classe e `mesa12` é objeto  
    c) `Mesa` é objeto e `mesa12` é classe  
    d) Ambos são métodos

19. Qual alternativa apresenta um conjunto coerente para uma classe `Filme`?
    a) `titulo`, `duracao`, `reproduzir()`  
    b) `assistir()`, `pausar()`, `reproduzir()` apenas como atributos  
    c) `Filme`, `Cinema`, `Sala` como atributos obrigatórios  
    d) `titulo()`, `duracao()`, `ano()` como classes

20. Uma classe `Funcionario` possui `nome`, `salario` e `calcularPagamento()`. Qual alternativa identifica corretamente esses elementos?
    a) Dois métodos e um atributo  
    b) Dois atributos e um método  
    c) Três atributos  
    d) Três métodos

21. Considere as classes `Animal` e `Cachorro`, sendo `Cachorro` uma especialização de `Animal`. Qual afirmação é correta?
    a) `Animal` pode reunir características comuns utilizadas por `Cachorro`  
    b) `Animal` precisa possuir todas as características específicas de `Cachorro`  
    c) As duas classes não podem compartilhar métodos  
    d) `Cachorro` precisa ser um objeto de `Animal`

22. Qual par de classes apresenta uma relação de herança mais coerente?
    a) `Funcionario` e `Gerente`  
    b) `Carro` e `Motor`  
    c) `Pedido` e `Produto`  
    d) `Aluno` e `Disciplina`

23. Em uma hierarquia formada por `Veiculo`, `Carro` e `Moto`, qual organização é mais adequada?
    a) `Carro` e `Moto` podem especializar `Veiculo`  
    b) `Veiculo` deve especializar `Carro`  
    c) `Moto` deve especializar `Carro`  
    d) As três classes devem ser objetos umas das outras

24. Uma vantagem da herança é:
    a) Permitir o reaproveitamento de características comuns entre classes relacionadas  
    b) Fazer com que todos os objetos tenham os mesmos valores  
    c) Eliminar a necessidade de métodos  
    d) Transformar atributos em objetos automaticamente

25. Considere `Pessoa`, `Aluno` e `Professor`. Qual estrutura faz mais sentido?
    a) `Aluno` e `Professor` especializam `Pessoa`  
    b) `Pessoa` especializa `Aluno` e `Professor` simultaneamente  
    c) `Aluno` especializa `Professor`  
    d) `Professor` especializa `Aluno`

26. Em uma hierarquia, uma subclasse:
    a) Pode possuir características próprias além das herdadas  
    b) Deve ser idêntica à superclasse  
    c) Não pode possuir métodos  
    d) Não pode possuir atributos

27. Qual alternativa apresenta uma relação pouco adequada para herança?
    a) `Cachorro` e `Animal`  
    b) `Gerente` e `Funcionario`  
    c) `Carro` e `Motor`  
    d) `Professor` e `Pessoa`

28. Em uma aplicação, `ContaCorrente` e `ContaPoupanca` compartilham `numero` e `saldo`, definidos em `Conta`. Essa organização exemplifica:
    a) Herança  
    b) Instanciação  
    c) Criação de atributos locais  
    d) Criação de objetos independentes

29. Se várias classes apresentam as mesmas características gerais, uma solução orientada a objetos pode ser:
    a) Criar uma classe mais geral para reunir essas características  
    b) Duplicar os mesmos atributos em todas as classes obrigatoriamente  
    c) Transformar todas as classes em métodos  
    d) Remover as características compartilhadas

30. Considere `Forma`, `Circulo` e `Retangulo`. Qual alternativa representa uma organização baseada em herança?
    a) `Circulo` e `Retangulo` são especializações de `Forma`  
    b) `Forma` é um objeto de `Circulo`  
    c) `Retangulo` é um atributo de `Circulo`  
    d) `Forma` é um método de `Retangulo`

31. O conceito de abstração em Orientação a Objetos está relacionado a:
    a) Representar apenas as características relevantes de uma entidade para o problema  
    b) Representar obrigatoriamente todos os detalhes de uma entidade real  
    c) Criar apenas métodos sem atributos  
    d) Impedir a existência de subclasses

32. Ao modelar um aluno em um sistema acadêmico, foram escolhidos apenas `nome`, `matricula` e `curso`. Características como altura e cor dos olhos foram ignoradas. Isso exemplifica:
    a) Abstração  
    b) Herança  
    c) Instanciação  
    d) Criação de método

33. Em um sistema bancário, qual conjunto de características seria mais relevante para representar uma `ContaBancaria`?
    a) Número da conta, saldo e titular  
    b) Cor favorita do titular, altura e peso  
    c) Marca do celular do titular e tamanho do calçado  
    d) Nome dos vizinhos do titular

34. Ao criar uma classe `Produto` para um sistema de estoque, qual informação é menos relevante para a abstração desse domínio?
    a) Código  
    b) Quantidade em estoque  
    c) Preço  
    d) Cor favorita do fabricante

35. Uma boa abstração depende principalmente:
    a) Do objetivo e do contexto do sistema  
    b) Da quantidade máxima possível de atributos  
    c) Da eliminação de todos os métodos  
    d) Do uso obrigatório de herança

36. Em um aplicativo de transporte, uma classe `Motorista` contém `nome`, `CNH` e `avaliacao`. Por que informações como o filme favorito do motorista podem ser ignoradas?
    a) Porque não são relevantes para o objetivo principal do sistema  
    b) Porque uma classe pode possuir no máximo três atributos  
    c) Porque atributos de texto não podem ser usados  
    d) Porque toda informação pessoal deve ser um método

37. Dois sistemas diferentes podem representar a mesma entidade com atributos diferentes porque:
    a) Cada sistema pode precisar abstrair aspectos diferentes dessa entidade  
    b) Uma classe nunca pode possuir os mesmos atributos em sistemas diferentes  
    c) Objetos não podem representar entidades reais  
    d) Herança obriga cada sistema a utilizar estruturas diferentes

38. Em um jogo, a classe `Personagem` utiliza `vida`, `forca` e `velocidade`. Dados como CPF e endereço não foram incluídos. Essa decisão demonstra:
    a) Seleção de características relevantes para a abstração  
    b) Uso incorreto de atributos  
    c) Ausência de orientação a objetos  
    d) Obrigatoriedade de herança

39. Em um sistema veterinário, qual conjunto representa melhor uma abstração de `Animal`?
    a) Nome, espécie, idade e peso  
    b) Número da conta bancária do dono, profissão do dono e modelo do carro do dono  
    c) Endereço da clínica, salário do veterinário e horário de funcionamento  
    d) Nome do fabricante do computador utilizado na recepção

40. Considere uma classe geral `Funcionario` e as classes `Professor` e `Secretario`. `Funcionario` contém `nome` e `salario`, enquanto cada especialização adiciona características próprias. Quais conceitos aparecem principalmente nesse exemplo?
    a) Abstração e herança  
    b) Objeto e método apenas  
    c) Atributo e instanciação apenas  
    d) Método e objeto apenas

# Atividade Prática - Diagramas de Sequência com PlantUML

**Disciplina:** Engenharia de Software  
**Tema:** UML — Diagramas de Sequência.


# Ferramenta: PlantUML

O PlantUML permite criar diagramas UML escrevendo comandos de texto.

**Ferramentas online:**

- [PlantText](https://www.planttext.com/)

- [PlantUML Online](https://plantuml.online/)

- [OmniUML](https://onuml.com/plantuml-online)

- [Documentação oficial de Diagramas de Sequência](https://plantuml.com/sequence-diagram)


**Como utilizar:**

1. Abra o editor online.

2. Apague o exemplo inicial, caso exista.

3. Copie um dos códigos `plantuml` apresentados nesta atividade.

4. Gere/atualize o diagrama no editor.

5. Observe como cada comando aparece visualmente.

6. Modifique o código e gere novamente o diagrama.

7. Ao concluir um exercício, salve o **código-fonte** e exporte uma **imagem do diagrama**.

> **Importante:** PlantUML não é uma linguagem de programação para construir o sistema. É uma linguagem textual usada para **descrever o diagrama**.


# PARTE 1 — EXEMPLOS GUIADOS

Nesta parte, utilizaremos uma plataforma de streaming semelhante à **Netflix**.

O primeiro cenário é **simples**, com mensagens e retornos. O segundo acrescenta **verificações, caminhos alternativos e uma ação opcional**.

## 1. A estrutura mínima de um Diagrama de Sequência

Todo diagrama começa com `@startuml` e termina com `@enduml`.

```
@startuml  
actor Usuario  
participant Sistema  
  
Usuario -\> Sistema: realizarAcao()  
  
@enduml
```

### O que significa cada elemento?

| Comando | Significado |
| - | - |
| `@startuml` | Início do diagrama. |
| `@enduml` | Fim do diagrama. |
| `actor Usuario` | Declara um ator externo. |
| `participant Sistema` | Declara um participante da interação. |
| `A -\> B: mensagem()` | A envia uma mensagem/chamada a B. |
| `B --\> A: resposta` | B devolve uma resposta a A. |
| `alt ... else ... end` | Representa caminhos alternativos. |
| `opt ... end` | Representa uma interação opcional. |
| `loop ... end` | Representa repetição. |


A ordem em que as mensagens aparecem no código será a ordem em que aparecerão no diagrama. **O tempo avança de cima para baixo.**


# Exemplo guiado 1 — Consultar detalhes de um filme

## 2. Leia o cenário

Em uma plataforma de streaming, um assinante seleciona um filme para consultar seus detalhes antes de reproduzi-lo.

O processo funciona assim:

1. O assinante seleciona um filme na tela de catálogo.

2. A tela solicita ao catálogo os dados do filme selecionado.

3. O catálogo solicita ao objeto do filme seus detalhes.

4. O filme retorna informações como título, sinopse e duração.

5. O catálogo devolve esses dados à tela.

6. A tela apresenta os detalhes ao assinante.

**Objetivo do diagrama:** representar **a consulta aos detalhes de um filme**, e não todo o funcionamento da plataforma.

## 3. Passo 1 — Identifique os participantes

Pergunte: *quem participa dessa interação?*

| Participante | Papel no cenário |
| - | - |
| `Assinante` | Pessoa que inicia a consulta. |
| `TelaCatalogo` | Interface usada pelo assinante. |
| `Catalogo` | Responsável por localizar o filme. |
| `Filme` | Contém os detalhes do conteúdo. |


Crie o diagrama apenas com os participantes:

```
@startuml  
  
actor Assinante  
participant TelaCatalogo  
participant Catalogo  
participant Filme  
  
@enduml
```

**Experimente:** copie esse código no editor. Observe as linhas verticais (*lifelines*) que representam cada participante.

## 4. Passo 2 — Adicione a primeira mensagem

O assinante seleciona um filme na interface.

A mensagem será:

```
Assinante -\> TelaCatalogo: selecionarFilme(idFilme)
```

Adicione-a ao código:

```
@startuml  
  
actor Assinante  
participant TelaCatalogo  
participant Catalogo  
participant Filme  
  
Assinante -\> TelaCatalogo: selecionarFilme(idFilme)  
  
@enduml
```

**Observe:** a seta parte de `Assinante` e aponta para `TelaCatalogo`.

## 5. Passo 3 — Encaminhe a solicitação

A interface não possui necessariamente os dados do filme. Ela solicita a consulta ao catálogo.

Adicione:

```
TelaCatalogo -\> Catalogo: buscarFilme(idFilme)
```

O catálogo, por sua vez, solicita os detalhes ao filme:

```
Catalogo -\> Filme: obterDetalhes()
```

Até aqui, o trecho principal ficará assim:

```
Assinante -\> TelaCatalogo: selecionarFilme(idFilme)  
TelaCatalogo -\> Catalogo: buscarFilme(idFilme)  
Catalogo -\> Filme: obterDetalhes()
```

**Repare:** as mensagens são inseridas na ordem em que as ações acontecem.

## 6. Passo 4 — Adicione os retornos

Agora os dados precisam voltar até a interface.

Use a seta tracejada `--\>` para representar os retornos:

```
Filme --\> Catalogo: titulo, sinopse, duracao  
Catalogo --\> TelaCatalogo: detalhesFilme  
TelaCatalogo --\> Assinante: exibirDetalhes()
```

A sequência das respostas segue o caminho de volta.

## 7. Passo 5 — Execute o código completo

Copie o código abaixo, gere o diagrama e compare com o cenário descrito.

```
@startuml  
  
title Consultar detalhes de um filme  
  
actor Assinante  
participant TelaCatalogo  
participant Catalogo  
participant Filme  
  
Assinante -\> TelaCatalogo: selecionarFilme(idFilme)  
  
TelaCatalogo -\> Catalogo: buscarFilme(idFilme)  
Catalogo -\> Filme: obterDetalhes()  
  
Filme --\> Catalogo: titulo, sinopse, duracao  
Catalogo --\> TelaCatalogo: detalhesFilme  
TelaCatalogo --\> Assinante: exibirDetalhes()  
  
@enduml
```


# Exemplo guiado 2 — Iniciar a reprodução de um filme

## 8. Leia o novo cenário

Um assinante escolhe um filme e solicita sua reprodução.

O sistema realiza as seguintes operações:

1. O assinante solicita a reprodução na tela do player.

2. A tela encaminha a solicitação ao serviço de reprodução.

3. O serviço verifica se a **conta possui assinatura ativa**.

4. **Se a assinatura estiver inativa**, a tela informa que a reprodução não está disponível.

5. **Se a assinatura estiver ativa**, o serviço pergunta ao perfil se o conteúdo é permitido para sua faixa etária.

6. **Se o perfil não puder assistir ao filme**, a tela informa que o conteúdo está bloqueado.

7. **Se o perfil estiver autorizado**, o serviço solicita ao filme o endereço do conteúdo.

8. O filme retorna o endereço de reprodução.

9. O serviço orienta a tela a iniciar a reprodução.

10. **Opcionalmente**, se o assinante tiver ativado legendas, a tela solicita as legendas do filme e as exibe.

11. A tela informa ao assinante que a reprodução foi iniciada.

Esse cenário é mais complexo porque existem **decisões e uma etapa opcional**.

## 9. Passo 1 — Identifique os participantes

| Participante | Responsabilidade |
| - | - |
| `Assinante` | Solicita a reprodução. |
| `TelaPlayer` | Interface de reprodução. |
| `ServicoReproducao` | Coordena a operação. |
| `Conta` | Informa se a assinatura está ativa. |
| `Perfil` | Verifica se o conteúdo é permitido. |
| `Filme` | Fornece o endereço do vídeo e as legendas. |


Comece com:

```
@startuml  
  
actor Assinante  
participant TelaPlayer  
participant ServicoReproducao  
participant Conta  
participant Perfil  
participant Filme  
  
@enduml
```

## 10. Passo 2 — Represente a solicitação inicial

O assinante solicita a reprodução e a interface repassa o pedido ao serviço:

```
Assinante -\> TelaPlayer: reproduzirFilme(idFilme)  
TelaPlayer -\> ServicoReproducao: solicitarReproducao(idPerfil, idFilme)
```

O serviço verifica a assinatura:

```
ServicoReproducao -\> Conta: assinaturaAtiva()  
Conta --\> ServicoReproducao: ativa
```

Nesse momento, temos duas possibilidades: assinatura ativa ou inativa.

## 11. Passo 3 — Adicione a primeira decisão com `alt`

O fragmento `alt` representa uma escolha entre diferentes caminhos.

```
alt assinatura ativa  
    ' Mensagens que acontecem se a assinatura estiver ativa  
else assinatura inativa  
    ServicoReproducao --\> TelaPlayer: assinaturaInativa  
    TelaPlayer --\> Assinante: informarAssinaturaInativa()  
end
```

**Importante:** somente um dos caminhos será executado. O texto após `alt` e `else` descreve as condições.

Por enquanto, o primeiro caminho ainda está incompleto. Vamos preenchê-lo.

## 12. Passo 4 — Verifique a permissão do perfil

No caminho da assinatura ativa, o serviço precisa verificar se o perfil pode assistir ao filme:

```
ServicoReproducao -\> Perfil: podeAssistir(idFilme)  
Perfil --\> ServicoReproducao: permitido
```

Essa resposta também pode ter dois resultados. Portanto, precisamos de **outro `alt` dentro do primeiro**:

```
alt perfil autorizado  
    ' A reprodução poderá ser iniciada  
else perfil bloqueado  
    ServicoReproducao --\> TelaPlayer: acessoBloqueado  
    TelaPlayer --\> Assinante: informarRestricao()  
end
```

Observe que uma decisão pode estar **dentro de outra decisão**.

## 13. Passo 5 — Inicie a reprodução

Quando a assinatura está ativa **e** o perfil está autorizado, o serviço pode obter o endereço do vídeo:

```
ServicoReproducao -\> Filme: obterEnderecoReproducao()  
Filme --\> ServicoReproducao: enderecoVideo  
  
ServicoReproducao -\> TelaPlayer: iniciarVideo(enderecoVideo)
```

Coloque essas mensagens dentro do caminho `alt perfil autorizado`.

## 14. Passo 6 — Adicione uma etapa opcional com `opt`

O assinante pode ter habilitado legendas.

Elas **não precisam ser carregadas em todas as reproduções**. Representamos isso com `opt`:

```
opt legendas habilitadas  
    TelaPlayer -\> Filme: obterLegendas(idioma)  
    Filme --\> TelaPlayer: legendas  
    TelaPlayer -\> TelaPlayer: exibirLegendas()  
end
```

A mensagem de `TelaPlayer` para si mesma é uma **autochamada**. Ela indica que o próprio participante executa uma operação.

Depois da etapa opcional, o player informa o resultado ao assinante:

```
TelaPlayer --\> Assinante: informarReproducaoIniciada()
```

## 15. Passo 7 — Execute o diagrama completo

**Atenção aos `end`:** cada bloco `alt` ou `opt` precisa ser encerrado. Como há um `alt` dentro de outro, teremos dois encerramentos para as decisões.

```
@startuml  
  
title Iniciar reproducao de um filme  
  
actor Assinante  
participant TelaPlayer  
participant ServicoReproducao  
participant Conta  
participant Perfil  
participant Filme  
  
Assinante -\> TelaPlayer: reproduzirFilme(idFilme)  
TelaPlayer -\> ServicoReproducao: solicitarReproducao(idPerfil, idFilme)  
  
ServicoReproducao -\> Conta: assinaturaAtiva()  
Conta --\> ServicoReproducao: ativa  
  
alt assinatura ativa  
  
    ServicoReproducao -\> Perfil: podeAssistir(idFilme)  
    Perfil --\> ServicoReproducao: permitido  
  
    alt perfil autorizado  
  
        ServicoReproducao -\> Filme: obterEnderecoReproducao()  
        Filme --\> ServicoReproducao: enderecoVideo  
  
        ServicoReproducao -\> TelaPlayer: iniciarVideo(enderecoVideo)  
  
        opt legendas habilitadas  
            TelaPlayer -\> Filme: obterLegendas(idioma)  
            Filme --\> TelaPlayer: legendas  
            TelaPlayer -\> TelaPlayer: exibirLegendas()  
        end  
  
        TelaPlayer --\> Assinante: informarReproducaoIniciada()  
  
    else perfil bloqueado  
  
        ServicoReproducao --\> TelaPlayer: acessoBloqueado  
        TelaPlayer --\> Assinante: informarRestricao()  
  
    end  
  
else assinatura inativa  
  
    ServicoReproducao --\> TelaPlayer: assinaturaInativa  
    TelaPlayer --\> Assinante: informarAssinaturaInativa()  
  
end  
  
@enduml
```


# 16. Outro comando importante — Repetição com `loop`

Em alguns cenários, uma operação precisa ocorrer várias vezes.

Imagine que a plataforma deseja consultar as informações de todos os episódios de uma temporada:

1. A tela solicita ao catálogo os episódios da temporada.

2. O catálogo retorna uma lista de episódios.

3. Para **cada episódio**, a tela consulta seus detalhes.

4. Ao final, a tela apresenta a lista completa ao assinante.

O `loop` permite representar essa repetição:

```
@startuml  
  
title Consultar episodios de uma temporada  
  
actor Assinante  
participant TelaSerie  
participant Catalogo  
participant Episodio  
  
Assinante -\> TelaSerie: abrirTemporada(idTemporada)  
TelaSerie -\> Catalogo: listarEpisodios(idTemporada)  
Catalogo --\> TelaSerie: listaEpisodios  
  
loop para cada episodio da lista  
    TelaSerie -\> Episodio: obterDetalhes(idEpisodio)  
    Episodio --\> TelaSerie: detalhesEpisodio  
end  
  
TelaSerie --\> Assinante: exibirListaDeEpisodios()  
  
@enduml
```

O bloco `loop` indica que as mensagens dentro dele se repetem **uma vez para cada episódio**.

Você utilizará `loop` no exercício mais elaborado da segunda parte.


# 17. Método para construir qualquer Diagrama de Sequência

Antes de desenhar, siga sempre esta sequência:

| Passo | Pergunta |
| - | - |
| **1. Definir o cenário** | Qual ação específica será representada? |
| **2. Identificar os participantes** | Quem inicia? Quais objetos ou serviços colaboram? |
| **3. Encontrar a primeira mensagem** | O que faz a interação começar? |
| **4. Organizar o fluxo principal** | Quais mensagens acontecem e em qual ordem? |
| **5. Adicionar retornos** | Que informações precisam voltar aos participantes? |
| **6. Identificar decisões** | Existem caminhos diferentes? Use `alt`. |
| **7. Identificar ações opcionais** | Existe algo que pode acontecer ou não? Use `opt`. |
| **8. Identificar repetições** | Existe uma ação repetida? Use `loop`. |
| **9. Conferir o resultado** | O diagrama corresponde ao texto do cenário? |



# PARTE 2 — ATIVIDADE PRÁTICA

## 18. Novo cenário — Sistema de Reservas de Salas de Estudo

Uma universidade deseja criar um sistema para que seus estudantes consultem e reservem salas de estudo.

O sistema permitirá consultar informações das salas, reservar horários e cancelar reservas. Algumas salas são bastante procuradas e possuem uma lista de espera para horários ocupados.

O sistema possui os seguintes participantes e responsabilidades:

| Participante | Responsabilidade |
| - | - |
| `Estudante` | Pessoa que utiliza o sistema. |
| `PortalReservas` | Interface utilizada pelo estudante. |
| `CatalogoSalas` | Localiza salas e apresenta informações sobre elas. |
| `Sala` | Armazena dados da sala e controla seus horários disponíveis. |
| `ServicoReservas` | Coordena reservas e cancelamentos. |
| `Reserva` | Armazena uma reserva e seu estado. |
| `ListaEspera` | Mantém os estudantes interessados em horários indisponíveis. |
| `Notificador` | Envia avisos aos estudantes. |


**Observação:** cada diagrama deve conter apenas os participantes necessários àquele cenário. Não é obrigatório utilizar todos em todos os exercícios.

Os diagramas devem representar as interações descritas abaixo. **Não é necessário programar o sistema.**


# Exercício 1 — Consultar informações de uma sala

## Cenário

Um estudante deseja consultar as informações de uma sala de estudo.

O processo funciona assim:

1. O estudante seleciona uma sala no portal.

2. O portal solicita ao catálogo que localize a sala.

3. O catálogo consulta os dados do objeto `Sala`.

4. A sala retorna seu **nome, capacidade e localização**.

5. O catálogo devolve essas informações ao portal.

6. O portal apresenta os detalhes ao estudante.


Construa um Diagrama de Sequência em PlantUML que represente esse cenário.

**O diagrama deve conter:**

- os participantes necessários;

- a mensagem que inicia o cenário;

- chamadas entre os objetos;

- retornos;

- a apresentação final das informações ao estudante.


# Exercício 2 — Reservar uma sala

## Cenário

Um estudante deseja reservar uma sala para uma determinada data e horário.

O processo funciona assim:

1. O estudante informa no portal a **sala, a data e o horário** desejados.

2. O portal encaminha a solicitação ao serviço de reservas.

3. O serviço pergunta à sala se o horário solicitado está disponível.

4. A sala responde informando se o horário está livre ou ocupado.

5. **Se o horário estiver livre:**

   - o serviço registra uma nova `Reserva` para o estudante, a sala, a data e o horário;

   - a reserva retorna seu identificador;

   - o serviço confirma a reserva ao portal;

   - o portal informa ao estudante que a reserva foi realizada.

6. **Se o horário estiver ocupado:**

   - o serviço informa que não foi possível reservar;

   - o portal apresenta uma mensagem de indisponibilidade ao estudante.


Construa um Diagrama de Sequência em PlantUML com os dois resultados possíveis.

**O diagrama deve conter:**

- mensagens e retornos;

- a verificação de disponibilidade;

- **um bloco `alt`** com os caminhos *horário livre* e *horário ocupado*;

- a confirmação ou a mensagem de erro correspondente.


# Exercício 3 — Cancelar uma reserva e avisar a lista de espera

## Cenário

Um estudante deseja cancelar uma reserva que já realizou. Caso exista uma lista de espera para o horário liberado, as pessoas interessadas deverão receber uma notificação.

O processo funciona assim:

1. O estudante seleciona uma reserva e solicita seu cancelamento no portal.

2. O portal encaminha a solicitação ao serviço de reservas, informando o estudante e a reserva.

3. O serviço consulta o objeto `Reserva` para verificar se a reserva **pertence ao estudante**.

4. **Se a reserva não pertencer ao estudante:**

   - o serviço rejeita a solicitação;

   - o portal informa que o estudante não possui permissão para cancelar aquela reserva;

   - o cenário é encerrado.

5. **Se a reserva pertencer ao estudante:**

   - o serviço verifica se a reserva **ainda está ativa**;

   - se já estiver cancelada, o portal informa que a reserva não está ativa;

   - se estiver ativa, o serviço solicita o cancelamento à reserva;

   - a reserva confirma que foi cancelada;

   - o serviço solicita à sala que libere o horário anteriormente ocupado.

6. Depois do cancelamento, o serviço consulta a `ListaEspera` para obter os estudantes interessados naquele horário.

7. **Se existirem estudantes na lista de espera:**

   - para **cada estudante interessado**, o serviço solicita ao `Notificador` o envio de uma mensagem informando que o horário foi liberado;

   - o `Notificador` confirma o envio de cada mensagem.

8. **Opcionalmente**, se o estudante que cancelou a reserva solicitou um comprovante, o serviço solicita ao `Notificador` o envio de uma confirmação de cancelamento.

9. Ao final do cancelamento bem-sucedido, o portal informa ao estudante que a reserva foi cancelada.

## Sua tarefa

Construa um Diagrama de Sequência que represente **todos os caminhos possíveis**.

**O diagrama deve conter:**

- os participantes necessários;

- mensagens e retornos;

- **um `alt`** para verificar se a reserva pertence ao estudante;

- **outro `alt`** para verificar se a reserva está ativa;

- **um `opt`** para representar a existência de estudantes na lista de espera;

- **um `loop` dentro desse `opt`** para enviar uma notificação a cada interessado;

- **outro `opt`** para o envio do comprovante de cancelamento;

- mensagens diferentes para sucesso e para cada situação de erro.

### Roteiro sugerido

**Passo 1 — Fluxo inicial**

Represente a solicitação de cancelamento e a verificação de propriedade da reserva.

**Passo 2 — Primeira decisão**

Utilize `alt` para diferenciar:

- reserva pertence ao estudante;

- reserva não pertence ao estudante.

**Passo 3 — Segunda decisão**

Dentro do caminho autorizado, utilize outro `alt`:

- reserva ativa;

- reserva já cancelada.

**Passo 4 — Cancelamento**

No caminho autorizado e ativo, represente:

- cancelar a reserva;

- receber a confirmação;

- liberar o horário na sala.

**Passo 5 — Lista de espera**

Represente a consulta à lista de espera. Use:

- `opt` se existirem estudantes interessados;

- `loop` para percorrer os interessados e enviar os avisos.

**Passo 6 — Comprovante opcional**

Adicione outro bloco `opt` para enviar o comprovante, caso solicitado.

**Passo 7 — Resultado**

Apresente a confirmação final ao estudante somente quando o cancelamento tiver sido realizado.


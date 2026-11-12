
@startuml

hide footbox
skinparam actorStyle awesome
skinparam BoxPadding 10
skinparam maxMessageSize 200
skinparam DefaultTextAlignment center
skinparam sequenceMessageAlign direction

title Diagrama de Sequência

actor "Usuário" AS Usuario

participant "InterfacePlayer" AS InterfacePlayer
participant "ServicoReproducao" AS ServicoReproducao
participant "Assinatura" AS Assinatura
participant "Musica" AS Musica
participant "Reproducao" AS Reproducao
participant "Favoritas" AS Favoritas

Usuario -> InterfacePlayer: Seleciona uma música para reprodução

InterfacePlayer -> ServicoReproducao: reproduzirMusica(idUsuario, idMusica)
activate ServicoReproducao

ServicoReproducao -> Assinatura: estaAtiva()

alt assinatura está ativa
  
  Assinatura --> ServicoReproducao:true

  ServicoReproducao -> Musica: reproduzir()
  ServicoReproducao -> Reproducao: registrarReproducao(idUsuario, idMusica)
  ServicoReproducao --> InterfacePlayer: musica em execução
  
  loop enquanto o usuario nao parar a reprodução
    ServicoReproducao -> ServicoReproducao: buscarProximaMusica()
    ServicoReproducao --> ServicoReproducao: idMusica
    ServicoReproducao -> Reproducao: registrarReproducao(idUsuario, idMusica)
    ServicoReproducao -> Musica: reproduzir()
  end
  
  opt favoritar
    Usuario -> InterfacePlayer: clica no botão favoritar
    InterfacePlayer -> ServicoReproducao: favoritarMusica()
    ServicoReproducao -> Favoritas: favoritar(idMusica)
  end

ServicoReproducao --> InterfacePlayer: parar reprodução

else assinatura está inativa
  Assinatura --> ServicoReproducao: false
  ServicoReproducao --> InterfacePlayer: assinatura está inativa

end

deactivate ServicoReproducao
@enduml

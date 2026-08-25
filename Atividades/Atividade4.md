# Corretor Automático de Provas - Modelagem UML

Este documento contém a modelagem UML (Unified Modeling Language) utilizando **PlantUML** para o sistema "Corretor Automático de Provas". A proposta é simular um processo completo de correção objetiva automatizada.

## 1. Diagrama de Casos de Uso

Mapeia as principais interações dos atores (Professor, Scanner e Sistema de Gestão) com as funcionalidades do sistema.

```plantuml
@startuml
left to right direction
actor Professor
actor "Scanner" as Scanner
actor "Sistema de Gestão Acadêmica" as SGA

usecase "Login do professor" as UC1
usecase "Cadastro de Gabarito" as UC2
usecase "Validação do Gabarito" as UC3
usecase "Digitalização da prova" as UC4
usecase "Correção automatizada" as UC5
usecase "Cálculo da nota" as UC6
usecase "Lançamento de nota no sistema" as UC7
usecase "Geração de relatório" as UC8

Professor --> UC1
Professor --> UC2
UC2 ..> UC3 : <<include>>
Professor --> UC4
Scanner --> UC4
UC4 ..> UC5 : <<include>>
UC5 ..> UC6 : <<include>>
UC6 ..> UC7 : <<include>>
UC7 --> SGA
Professor --> UC8
UC8 --> SGA
@enduml
```

## 2. Diagrama de Classes

Estrutura das entidades obrigatórias, seus respectivos atributos, métodos principais e os relacionamentos.

```plantuml
@startuml
class Professor {
  - id: int
  - nome: String
  + login(): boolean
  + cadastrarGabarito(): void
  + solicitarRelatorio(): void
}

class Scanner {
  - modelo: String
  + digitalizarProva(): Prova
}

class Gabarito {
  - idDaProva: int
  - respostas: List<String>
  + validarGabarito(): boolean
}

class Prova {
  - idAluno: int
  - arquivoImagem: String
  + obterRespostas(): List<RespostaAluno>
}

class RespostaAluno {
  - numeroQuestao: int
  - alternativaMarcada: char
}

class Corretor {
  + corrigir(prova: Prova, gabarito: Gabarito): double
  + calcularNota(acertos: int): double
}

class SistemaGestao {
  - urlBase: String
  + registrarNota(idAluno: int, nota: double): void
  + gerarRelatorio(idTurma: int): Relatorio
}

Professor "1" -- "1..*" Gabarito : cadastra >
Professor "1" -- "1" Scanner : utiliza >
Scanner "1" -- "1..*" Prova : digitaliza >
Prova "1" *-- "1..*" RespostaAluno : contém
Corretor "1" -- "1" Gabarito : consulta >
Corretor "1" -- "1..*" Prova : corrige >
Corretor "1" -- "1" SistemaGestao : envia notas >
@enduml
```

## 3. Diagrama de Atividades

Fluxo detalhado do processo completo, desde o acesso inicial até as validações lógicas e finalização.

```plantuml
@startuml
start
:Professor faz login;
:Cadastrar Gabarito;
if (Gabarito válido?) then (sim)
  :Iniciar digitalização;
  :Scanner lê a prova;
  if (Prova lida com sucesso?) then (sim)
    :Realizar correção automatizada;
    :Calcular nota;
    :Lançar nota no SGA;
    :Gerar relatórios;
  else (não)
    :Notificar erro de leitura;
  endif
else (não)
  :Solicitar novo gabarito;
endif
stop
@enduml
```

## 4. Diagrama de Sequência

Representa a linha do tempo da execução, demonstrando a troca de mensagens entre os componentes do sistema.

```plantuml
@startuml
actor Professor
participant App
participant Scanner
participant Corretor
participant "Sistema de Gestão" as SGA

Professor -> App: login()
App --> Professor: sucesso
Professor -> App: enviarGabarito(respostas)
App -> Corretor: validarGabarito()
Corretor --> App: gabaritoValido

Professor -> App: iniciarDigitalizacao()
App -> Scanner: capturarImagem()
Scanner --> App: imagemProva

App -> Corretor: corrigirProva(imagemProva, gabarito)
Corretor -> Corretor: calcularNota()
Corretor --> App: notaCalculada

App -> SGA: registrarNota(idAluno, nota)
SGA --> App: notaRegistrada

Professor -> App: solicitarRelatorio()
App -> SGA: buscarDadosRelatorio()
SGA --> App: dadosRelatorio
App --> Professor: exibirRelatorio()
@enduml
```

---

[PDF da Atividade Preenchida](../Assets/PDFs/Corretor%20Automático%20de%20Provas%20-%20Entrega.pdf)
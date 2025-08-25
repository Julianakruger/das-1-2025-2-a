# das-1-2025-2-a

# Aula 1 - 04/08/2025

- Padrões mitigam a complexidade
- Abstração: representação de um objeto da vida real, com características, com o propósito de resolver um problema.
- Padrões estão inclusos em: nomes de arquivos, pastas, 
- A POO permite ocultar informações pela visibilidade dos atributos
- Coesão: código com coesão faz uma coisa bem feita (somente a representação dos dados do arquivo)
- Acoplamento: dependência de uma classe com outra
- Autoacoplamento: instanciação e uso de um método no construtor de outra classe

UML:
- Flecha vazia: herança
- Flecha tracejada: implementação
- Flecha cheia: Associação


# Aula 2

- O que é SOLID?

Usar a orientação a objetos do jeito mais correto possível!

S — Single Responsibility Principle (Princípio da responsabilidade única)
O — Open-Closed Principle (Princípio Aberto-Fechado)
L — Liskov Substitution Principle (Princípio da substituição de Liskov)
I — Interface Segregation Principle (Princípio da Segregação da Interface)
D — Dependency Inversion Principle (Princípio da inversão da dependência)

Maneira de usar o conceito de responsábildiade única
M - Dados
V - HTML
C - Controla a Tela

MVC - apresentação de regas e negocios.


# Aula 3

O Princípio da Inversão de Dependência diz que módulos de alto nível não devem depender de módulos de baixo nível, ambos devem depender de abstrações (interfaces ou classes abstratas). Além disso, as abstrações não devem depender de detalhes, e sim os detalhes das abstrações. Isso reduz o acoplamento entre componentes, tornando o código mais flexível, testável e fácil de manter. Com o DIP, você consegue trocar implementações sem alterar a lógica principal do sistema, favorecendo a reutilização e evolução do código. É um dos princípios SOLID que ajuda a criar sistemas desacoplados e bem organizados.


Princípio da inversão da Dependência 

O Controller não liga direto na implementação, ele comunica com a interface primeiro

Evitar que uma classe fale diretamente com a outra 

Prefira composição a Herança 

Quando a gente deve usar herança?
R:     Animal
Gato    	Cachorro

Um gato nunca se tornará um cachorro, ou vice-versa.
Quando a relação não for estritamente hierárquica, prefira composição, ou seja, construir comportamentos combinando diferentes objetos, em vez de criar cadeias de herança profundas.

A composição oferece mais flexibilidade, evita acoplamento excessivo e facilita a reutilização de código.

--//--

Princípio de Demeter (Menor Conhecimento)
Também chamado de Law of Demeter.
A ideia é evitar dependências desnecessárias e não acessar diretamente objetos internos de outros objetos.
Fuja de variáveis globais e trabalhe com as informações locais e disponíveis no contexto atual.

  --/--
  
Princípio do Aberto/Fechado (Open/Closed Principle)
Um objeto deve proteger seu comportamento para que ninguém possa quebrá-lo alterando diretamente sua lógica interna.
A ideia é que quem cria a classe não quer que ela seja modificada, mas sim estendida com novas funcionalidades.

  --//-- 

  FB = A(esquerda) - A(direita)
A = 1 + max(AfilhoEsquerdo, AfilhoDireito)

40 - 20 - 60 - 10 - 30 - 25

Nó: 40
Raiz?: nulo
Nó inserido: raiz = 40
A = 1
Fb = 0

Nó: 20
raiz?: menor que 40
Nó inserido: raiz.filhoEsquerdo = 20
A = 1
Fb = 0
Volta, nó 40:
    A = 2
    Fb = 1


função inserir(No noAtual, int valor, No noPai) {
    No novoNo = new No(valor);

    if noAtual == null {
        noAtual = novoNo
    }

    if noAtual.fb > 1 {

    }

    if valor < noAtual.valor {
        noAtual.filhoEsquerdo = novoNo
    }
    if valor > noAtual.valor {
        noAtual.filhoDireito = novoNo
    }

    return novoNo

}

----

// For format details, see https://aka.ms/devcontainer.json. For config options, see the
// README at: https://github.com/devcontainers/templates/tree/main/src/java
{
  "name": "Java",
  // Or use a Dockerfile or Docker Compose file. More info: https://containers.dev/guide/dockerfile
  "image": "mcr.microsoft.com/devcontainers/java:1-21-bullseye",

  "features": {
    "ghcr.io/devcontainers/features/java:1": {},
    "ghcr.io/devcontainers/features/azure-cli:1": {},
    "ghcr.io/devcontainers/features/docker-in-docker:2": {},
    "ghcr.io/dapr/cli/dapr-cli:0": {},
    "ghcr.io/devcontainers/features/python:1": {},
    "ghcr.io/devcontainers/features/aws-cli:1": {}
  },

  // Use 'forwardPorts' to make a list of ports inside the container available locally.
  // "forwardPorts": [],

  // Use 'postCreateCommand' to run commands after the container is created.
  // "postCreateCommand": "java -version",

  // Configure tool-specific properties.
  // "customizations": {},

  // Uncomment to connect as root instead. More info: https://aka.ms/dev-containers-non-root.
  // "remoteUser": "root"
  "appPort": [4000, 4200, 4433, 5000, 8080, 9876],
  "extensions": [
    "vscjava.vscode-java-pack",
    "vmware.vscode-boot-dev-pack",
    "humao.rest-client",
    "ms-azuretools.vscode-docker",
    "cweijan.vscode-database-client2",
    "ms-vscode.vscode-node-azure-pack",
    "ms-azuretools.vscode-dapr"
  ]
  //"hostRequirements": {
  //	"cpus": 4,
  //	"memory": "16gb"
  //}
}

--//--






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
- Aula 1 - 04/08/2025 !!
Principios de projeto de software - Capitulo 5 do livro

Padrões mitigam a complexidade

Abstração:
Seria representar algo do mundo real para resolver um problema

Config <-- configurações

Controller <-- html, api, rest

Entity <-- dados

Repository <-- Con db

Service <-- Lógica

Ocultamento de informação:
Não há necessidade de entender todo o funcionamento de um framework para poder usa-lo

Código Coeso (Coesão)
Um código que realiza uma tarefa muito bem feita! Elementos de um módulo (como classes, funções ou pacotes) estão relacionados e trabalham juntos para um propósito único e bem definido.

Acoplamento
Acoplamento: dependência de uma classe com outra
Autoacoplamento: instanciação e uso de um método no construtor de outra class
UML

Flecha vazia: herança
Flecha tracejada: implementação
Flecha cheia: Associação

---//---


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

O que é SOLID?

Usar a orientação a objetos do jeito mais correto possível!

S — Single Responsibility Principle (Princípio da responsabilidade única) O — Open-Closed Principle (Princípio Aberto-Fechado) L — Liskov Substitution Principle (Princípio da substituição de Liskov) I — Interface Segregation Principle (Princípio da Segregação da Interface) D — Dependency Inversion Principle (Princípio da inversão da dependência)

Maneira de usar o conceito de responsábildiade única M - Dados V - HTML C - Controlar a tela

package br.univille;

import javax.swing.JButton;
import javax.swing.JFrame;

public class Janelinha extends JFrame {

    private JButton botaozinho;
    private Controlador controlador;

    public Janelinha() {
        setTitle("Eu não acredito");
        setSize(500, 500);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        botaozinho = new JButton("ME CLICA");
        controlador = new Controlador();
        botaozinho.addActionListener(controlador);

        add(botaozinho);

        setVisible(true);
    }

    public static void main(String[] args) {
        new Janelinha();
    }
    package br.univille;

    import java.awt.event.ActionEvent;
    import java.awt.event.ActionListener;
    import javax.swing.JOptionPane;

    public class Controlador implements ActionListener {

    @Override
    public void actionPerformed(ActionEvent e) {
        meClica();
    }

    private void meClica() {
        JOptionPane.showMessageDialog(null, "NÃO ACREDITO");
    }
    }


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



#Aula 02/09

Resuma a diferençca entre: Arquitetura e Design

A diferença entre arquitetura e design, muitas vezes, acaba ficando meio confusa, mas é algo essencial para quem quer pensar como arquiteto. O texto deixa bem claro que pensar como arquiteto não é só “pensar na arquitetura”, mas entender que arquitetura e design são coisas diferentes, que se complementam para resolver problemas técnicos e de negócio. A arquitetura está ligada ao quadro geral, ela tenta entender o que o negócio precisa, definir quais características o sistema deve ter, escolher os padrões e estilos certos para o problema e criar os grandes blocos que vão formar o sistema. Já o design é mais focado nos detalhes, na parte que a equipe de desenvolvimento vai cuidar: criar diagramas específicos, pensar nas telas, codificar e testar o software.

O problema é que, a arquitetura e o design ficaram separados, quase como se vivessem em mundos diferentes. O arquiteto cria a arquitetura e passa para o desenvolvedor, que faz o design, e a comunicação vai só em um sentido. Isso gera vários problemas, porque o arquiteto acaba desconectado da realidade do desenvolvimento, e quando o desenvolvedor faz mudanças, o arquiteto nem sempre fica sabendo — uma situação que dificulta que a arquitetura realmente funcione. Por isso, o texto defende que a solução é quebrar essas barreiras, fazendo com que arquitetos e desenvolvedores trabalhem juntos como uma equipe, mantendo uma comunicação constante. No modelo a arquitetura e design não são fases separadas, mas partes do mesmo ciclo, que evoluem juntas durante o projeto.

Então, a diferença entre arquitetura e design está no nível de foco e responsabilidade, mas para que o projeto dê certo, os dois precisam estar alinhados e colaborando o tempo todo.

--//--

Como é a formação do conhecimento de um arquiteto modelo T?

A formação do conhecimento de um arquiteto modelo T é bem diferente da de um desenvolvedor normal. Enquanto o desenvolvedor normalmente precisa se aprofundar em uma ou poucas tecnologias para fazer seu trabalho, tipo conhecer uma linguagem, um framework ou uma ferramenta a fundo, o arquiteto precisa ter uma visão mais ampla das possibilidades técnicas. O texto usa a imagem da pirâmide para isso: existe o que você sabe bem, o que você sabe que não sabe direito, e o que você nem sabe que não sabe que, na verdade, é a maior parte do que existe por aí.

No começo da carreira, o foco do desenvolvedor é justamente aumentar a parte do “o que você sabe” especializar para conseguir entregar soluções com qualidade. Já para o arquiteto, o ideal é ampliar muito o “meio da pirâmide”, ou seja, o que ele sabe que não sabe direito, para conhecer várias tecnologias, soluções e abordagens diferentes, mesmo que não domine todas profundamente. Isso ajuda a ter uma visão mais completa e saber quais opções escolher para cada problema.

A ideia do arquiteto modelo T é: ter uma base mais larga de conhecimento, com um pouco de profundidade em algumas áreas específicas. Essa combinação permite que o arquiteto entenda bem o todo e ainda tenha domínio suficiente para tomar decisões acertadas e práticas.

O texto também fala que muitos arquitetos acabam caindo em dois erros comuns: tentar ser especialista em tudo e não conseguir, ou ficar preso a conhecimentos antigos, sem se atualizar. Por isso, pensar como arquiteto é, em parte, saber abrir mão daquela especialização extrema em algumas tecnologias para ganhar uma visão mais ampla e atualizada, que realmente faça a diferença na hora de criar uma arquitetura que funcione para o negócio.


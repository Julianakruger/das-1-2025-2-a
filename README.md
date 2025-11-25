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


# Aula 3 - 11/08/2025 

 Princípio da Inversão de Dependência (Dependency Inversion Principle) Em vez de o Controller depender diretamente de uma implementação concreta, ele deve se comunicar primeiro com uma interface ou abstração. Isso evita o acoplamento direto entre classes, facilitando a manutenção, a troca de implementações e a realização de testes. A ideia central é: módulos de alto nível não devem depender de módulos de baixo nível, ambos devem depender de abstrações.

Prefira Composição à Herança
A herança deve ser usada apenas quando existe uma relação clara do tipo "é um" (is-a), por exemplo:

Animal → Gato

Animal → Cachorro

Um gato nunca se tornará um cachorro, ou vice-versa. Quando a relação não for estritamente hierárquica, prefira composição, ou seja, construir comportamentos combinando diferentes objetos, em vez de criar cadeias de herança profundas.

A composição oferece mais flexibilidade, evita acoplamento excessivo e facilita a reutilização de código.

--//--

# Princípio de Demeter (Menor Conhecimento)
Também chamado de Law of Demeter.

A ideia é evitar dependências desnecessárias e não acessar diretamente objetos internos de outros objetos. Fuja de variáveis globais e trabalhe com as informações locais e disponíveis no contexto atual.

--//--

# Princípio do Aberto/Fechado (Open/Closed Principle)
Um objeto deve proteger seu comportamento para que ninguém possa quebrá-lo alterando diretamente sua lógica interna. A ideia é que quem cria a classe não quer que ela seja modificada, mas sim estendida com novas funcionalidades.

Aberto para extensão, fechado para modificação Proteja o que a classe já faz, mas permita adicionar novos comportamentos sem alterar o código existente.

# Aula 4 - 12/08/2025
SOLID:

L: Princípio de substituição de Liskov - redefinição de métodos de classe base em classe filho (aplicado quando tem herança). Se há uma herança, com vários filhos, o código dos filhos deve ser feita de tal maneira a manter a compatibilidade com o pai, caso elas forem substituídas (sem quebrar o padrão que o pai tem) Filho(método x) -> Pai <- Filho2(Método x) | aplicar os dois filhos não quebra a classe

# Aula 6 - 26/08/2025
Para desenvolver um bom software, é fundamental construir uma estrutura sólida. Essa estrutura é definida por meio da arquitetura de software, que pode ser entendida a partir de três dimensões principais:

1 - Características da Arquitetura
São os requisitos não funcionais que direcionam o sistema, como:

Disponibilidade Confiabilidade Testabilidade Escalabilidade Segurança

Essas características não podem ser todas atendidas ao mesmo tempo; é preciso selecionar aquelas que melhor se adequam ao contexto do sistema.

2 - Decisões de Arquitetura
Correspondem às regras e padrões estabelecidos para garantir consistência no desenvolvimento. Sem essas definições, o software pode acumular problemas e se tornar difícil de manter. Exemplos de decisões arquiteturais:

Definir entre Monólito ou Microserviços Escolher padrões de integração e comunicação Definir políticas de versionamento

3 - Princípios de Design
São boas práticas e diretrizes que orientam o desenvolvimento dentro da arquitetura escolhida. Devem ser seguidos sempre que possível, garantindo que o sistema permaneça padronizado, compreensível e de fácil manutenção. Exemplos: separação de responsabilidades, coesão de módulos, baixo acoplamento.

# Aula 7 - 01/09/2025

# Arquitetura de Software

Quando falamos em construir software de qualidade, não dá para pensar só em código. É preciso ter uma arquitetura bem definida, que vai servir como base para o sistema crescer e se manter saudável ao longo do tempo.

# Características da Arquitetura
Essas são as chamadas qualidades não funcionais: disponibilidade, escalabilidade, segurança, desempenho, testabilidade… A verdade é: nenhum sistema consegue ser perfeito em tudo. Por isso, o arquiteto precisa escolher quais características são mais importantes para aquele projeto específico. Um exemplo bem clássico é decidir se o sistema vai ser Monolito ou Microserviços.

# Princípios de Design
Aqui entram as boas práticas que ajudam a manter o sistema limpo e organizado. São as “regras de convivência” do software, que guiam o time e evitam bagunça no futuro.

# O Papel do Arquiteto de Software
- O arquiteto não é só “o cara que desenha caixinhas”. Ele tem responsabilidades bem práticas, como:
- Tomar decisões difíceis: escolher tecnologias, justificar o porquê de cada decisão, pesar prós e contras.
- Olhar para o código constantemente: identificar onde precisa refatorar e quando vale a pena mexer.
- Estar sempre atualizado: acompanhar tendências, ver como novas tecnologias podem ajudar (ou atrapalhar).
- Garantir que o time siga os padrões: não adianta só decidir, é preciso manter disciplina. Testes e revisões de código ajudam nisso.
- Ter experiência e bagagem: boas decisões vêm muito da prática e de já ter passado por situações parecidas.
- Conhecer o negócio: não adianta ser só técnico, precisa entender o contexto do cliente.
- Saber lidar com pessoas: motivar, inspirar, negociar e até lidar com política dentro da empresa.

# DevOps na Arquitetura
Hoje em dia, não dá para falar de arquitetura sem citar DevOps. A ideia é simples: aproximar desenvolvimento e operações para entregar valor mais rápido ao cliente.

Planejamento: trabalhar em ciclos curtos, como no Scrum.
Integração Contínua: ter um repositório confiável e sempre atualizado.
Feedback constante: aprender com cada entrega, corrigir e melhorar.
Responsabilidade compartilhada: se o sistema cair, ninguém “joga a bomba” para o outro time. Todos trabalham juntos para resolver.



# Aula 02/09

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


# 08/09
Compensações (Trade-offs)
Sempre que se define uma arquitetura, não é possível atender a todas as demandas ao mesmo tempo.
Como se costuma dizer: “não existem respostas certas ou erradas, apenas compensações.”

# Arquitetura baseada em tópicos
- Funciona de forma semelhante a um grupo de família no WhatsApp
- Segue um padrão parecido com o Observer:
- Publisher → envia mensagens
- Subscriber(s) → recebem mensagens (um ou muitos)
- Os assinantes se inscrevem em um broker (tópico), que distribui as mensagens
- Caso o tópico saia do ar no momento da entrega, a mensagem pode ser perdida
- A inclusão de novos subscribers é simples, sem necessidade de mudanças na arquitetura

# Vantagens:

- Baixo acoplamento
- Facilidade de expansão

# Desvantagens:

- Rastreabilidade de problemas limitada
- Possibilidade de perda de mensagens

# Arquitetura baseada em filas
- Modelo: Sender <-> Fila <-> Receiver
- As mensagens são enviadas (enqueue) para a fila e consumidas (dequeue) pelo receiver
- Relação de 1 sender para 1 receiver
- Cada receiver possui sua própria fila, independente dos demais
- Garantia de entrega em ordem
- A fila funciona como buffer, armazenando mensagens temporariamente
- O receiver consulta a fila (polling) para buscar novas mensagens
- Ao incluir um novo receiver, é necessário:
    - Criar uma nova fila
    - Ajustar o sender
    - Conectar ambos
    - Isso gera maior impacto na arquitetura]
    
# Vantagens:

- Maior rastreabilidade de problemas
- Confiabilidade na entrega

# Desvantagens:

- Maior acoplamento
- Maior complexidade de manutenção



# 2° BIMESTRE

https://learn.microsoft.com/pt-br/azure/architecture/patterns/circuit-breaker?wt.mc_id=AZ-MVP-5003638

# 06/10/2025

Essas características cumprem três papéis principais:

- Tratam de questões de design que não estão ligadas diretamente às funções do sistema, mas sim à forma como ele é construído.

- Influenciam a estrutura do software, impactando decisões sobre componentes, integrações, segurança e desempenho.

- Definem a qualidade e o sucesso do projeto, garantindo que o sistema seja confiável, seguro e sustentável a longo prazo.

- Essas características podem ser agrupadas em três grandes categorias: operacionais, estruturais e transversais.

Características Operacionais

- São as que dizem respeito ao funcionamento do sistema no dia a dia.
Incluem:

- Disponibilidade – o tempo em que o sistema precisa estar ativo (por exemplo, 24 horas por dia).

- Continuidade – a capacidade de se recuperar de falhas graves ou desastres.

- Desempenho – o tempo de resposta e a eficiência ao processar informações.

- Recuperabilidade – o tempo necessário para voltar ao ar após uma falha.

- Confiabilidade e segurança – a capacidade de funcionar corretamente, sem falhas que comprometam dados.

- Robustez – a resistência a erros ou interrupções inesperadas.

- Escalabilidade – a capacidade de crescer e lidar com mais usuários ou demandas sem perder qualidade.

Características Estruturais

Estão relacionadas à organização interna do código e à sua facilidade de evolução.
Envolvem:

- Configuração – facilidade de ajustar o sistema para diferentes contextos.

- Extensibilidade – quão simples é adicionar novas funcionalidades.

- Reutilização – aproveitamento de partes do sistema em outros projetos.

- Portabilidade – possibilidade de rodar o software em diferentes ambientes.

- Manutenibilidade – facilidade de corrigir erros e fazer melhorias.

- Atualização – facilidade para lançar novas versões sem grandes impactos.

Características Transversais

Essas atravessam todo o sistema, afetando várias partes ao mesmo tempo.
Incluem:

- Acessibilidade – tornar o sistema utilizável por todos, inclusive pessoas com deficiência.

- Autenticação e autorização – controle de acesso e permissões de usuários.

- Privacidade e segurança – proteção dos dados e comunicações.

- Legalidade – cumprimento de normas e leis, como a LGPD.

- Usabilidade – facilidade de uso e boa experiência para o usuário.

- Armazenamento – gerenciamento correto de dados, inclusive exclusão quando necessário.

Além disso, a ISO (Organização Internacional para Padronização) define uma série de categorias que ajudam a medir a qualidade de um software. Entre elas estão:

- Eficiência de desempenho (resposta e uso de recursos),

- Compatibilidade (funcionar bem com outros sistemas),

- Usabilidade,

- Confiabilidade,

- Segurança,

- Manutenibilidade, e

- Portabilidade.

Porém, na prática, o arquiteto precisa lidar com conflitos entre características — chamados de trade-offs. Melhorar a segurança, por exemplo, pode reduzir o desempenho, já que criptografar dados exige mais processamento. Por isso, o papel do arquiteto é encontrar o equilíbrio.

Não existe uma arquitetura “perfeita”. O objetivo é construir a arquitetura mais equilibrada possível, que atenda às necessidades do negócio e ainda permita evolução contínua. Boas arquiteturas são aquelas que mudam com facilidade, acompanhando as descobertas e aprendizados do projeto.

 # 07/10/2025 
https://learn.microsoft.com/pt-br/azure/architecture/patterns/cqrs

CQRS
(Segregação de Responsabilidade de Comando e Consulta) é um padrão de design que segrega operações de leitura e gravação de um armazenamento de dados em modelos de dados separados. Essa abordagem permite que cada modelo seja otimizado de forma independente e pode melhorar o desempenho, a escalabilidade e a segurança de um aplicativo.

Usado quando atinge o limite da escalabilidade vertical da máquina
Estância primária - Somente para escrever (servidor 1)
Replica de leitura - Somente para ler (servidor 2)
O sistema poderá estar conectado com 2,3 ou mais bancos de dados
Podendo ter atrasos, pois a comunicação entre os bancos é assincrona

 # 09/10/2025 
https://learn.microsoft.com/pt-br/azure/architecture/patterns/retry

Estratégias de repetição
Se um aplicativo detectar uma falha ao tentar enviar uma solicitação para um serviço remoto, ele poderá lidar com falhas usando as seguintes estratégias:

CANCELAR (cancel)
Se a falha indica não ser transitória ou provavelmente não será bem-sucedida se for repetida, o aplicativo deve cancelar a operação e relatar uma exceção.

TENTE NOVAMENTE IMEDIATAMENTE (retry immediately)
Se a falha específica relatada for incomum ou rara, como um pacote de rede corrompido durante a transmissão, o melhor curso de ação poderá repetir imediatamente a solicitação.

TENTAR NOVAMENTE APÓS ATRASO (retry after delay)
Se a falha for causada por uma das falhas mais comuns de conectividade ou ocupado, a rede ou o serviço poderá precisar de um curto período enquanto os problemas de conectividade forem corrigidos ou a lista de pendências de trabalho for desmarcada, portanto, atrasar programaticamente a repetição é uma boa estratégia. Em muitos casos, deve ser escolhido o período entre as novas tentativas a fim de distribuir solicitações de várias instâncias do aplicativo da maneira mais uniforme possível para reduzir a chance de um serviço ocupado continuar sobrecarregado.

A GRANDE BOLA DE LAMA 
É um padrão de software que descreve um sistema desorganizado, sem uma estrutura arquitetural clara, onde componentes estão fortemente acoplados. Ele surge da falta de planejamento a longo prazo, levando a um código difícil de entender, manter e estender, tornando as alterações arriscadas e trabalhosas. 

ARQUITETURA UNITÁRIA
Software roda em um único computador
Sistemas embarcados (TV, geladeira, eletrodomésticos)

CLIENTE/SERVIDOR
O modelo cliente/servidor é uma arquitetura em que um cliente (um aplicativo ou dispositivo que solicita um serviço) se comunica com um servidor (um computador ou software que fornece o serviço e os dados). Os clientes iniciam as solicitações, e os servidores respondem com os recursos, dados ou serviços solicitados, como um navegador que pede uma página da web a um servidor web. 

DESKTOP + SERVIDOR DE BANCO DE DADOS (Cliente/ Servidor/ Database Centric)
Um grande Banco de dados parrudo com outras máquinas conectadas, cada máquina tem o software instalado nela mesmo. A lógica fica instalado na máquina (telas de cadastro) e no banco de dados (store procedure).
Para atualização, primeiro se atualiza o banco de dados, e depois se atualiza máquina por máquina.

NAVEGADOR + SERVIDOR WEB 
(web 1.0)
Banco de dados <===> Web Server <===> Máquina (navegação de HTML)
Cliente / Servidor / Web Server

web 2.0 (sistema distribuido)
máquina usuário recebe HTML e Json (aplicação rodando no cliente)
Web Server se torna uma API Rest (aplicação rodando no web server)

 # 10/10/2025 
https://learn.microsoft.com/pt-br/azure/architecture/patterns/retry

TRÊS CAMADAS
Uma arquitetura que ficou bem popular no final dos anos 1990 foi uma arquitetura de três camadas, que fornecia mais camadas de separação. Quando ferramentas como servidores de aplicação se tornaram populares em Java e .NET, as empresas começaram a criar ainda mais camadas na topologia: uma camada de banco de dados usando um servidor de banco de dados com capacidade industrial, uma camada de aplicação gerenciada por um servidor de aplicação, um front-end escrito em HTML gerado e cada vez mais JavaScript, conforme suas capacidades expandiam.

ARQUITETURAS MONOLÍTICAS VERSUS DISTRIBUÍDAS
Monolíto - sistema onde todas as funcionalidades estão em uma única base de código centralizado

LOG DISTRIBUÍDO
Um log distribuído é um registro de eventos ou mensagens mantido de forma consistente entre vários nós (máquinas) em um sistema distribuído. Ele funciona como uma sequência ordenada e imutável de registros que todos os participantes conseguem ler e seguir na mesma ordem.

TRANSAÇÕES DISTRIBUIDAS
Garante que todas as partes envolvidas em uma operação completem com sucesso ou todas sejam revertidas.

# 20/10/2025 

A arquitetura em camadas é um dos estilos mais comuns no desenvolvimento de software devido à sua simplicidade, familiaridade e baixo custo. Ela organiza o sistema em níveis, cada um com responsabilidades específicas, normalmente divididos em apresentação, negócios, persistência e banco de dados. Esse formato reflete naturalmente a estrutura de muitas organizações, o que contribui para sua adoção.

Há dois modelos de comunicação entre camadas: o estrito, em que cada camada só acessa a imediatamente inferior, e o relaxado, que permite saltos entre camadas, oferecendo flexibilidade, mas podendo aumentar o acoplamento. Entre suas vantagens estão a clareza organizacional, a separação de responsabilidades e a facilidade de testes. No entanto, ela pode se tornar rígida, dificultar escalabilidade independente e não se encaixar bem em arquiteturas distribuídas ou orientadas a eventos. É mais adequada para sistemas tradicionais de CRUD e aplicações corporativas, mas menos indicada para cenários modernos que exigem reatividade e alta flexibilidade.

# 27/10/2025  

PIPELINE
É uma sequência de etapas organizadas, onde cada etapa recebe uma entrada, processa algo e entrega a saída para a próxima etapa. É como uma “linha de montagem”, em que cada fase executa uma parte do trabalho até completar o resultado final. O mesmo é ideal para processamento contínuo, transformações em fluxo e tarefas que podem ser divididas em passos claros. Ele promove baixo acoplamento, alta coesão e reutilização de componentes.

# 03/11/2025 

ARQUITETURA MICROKERNEL
A arquitetura Microkernel divide o sistema em um núcleo mínimo, que contém apenas as funções essenciais, e um conjunto de plugins, que adicionam ou estendem funcionalidades. O núcleo é estável e simples, os plugins são modulares, podem ser trocados e evoluem sem afetar o restante do sistema. Esse estilo é ideal para plataformas extensíveis, como IDEs e sistemas que precisam de personalização constante.

# 10/11/2025

ARQUITETURA DE MICROSSERVIÇOS
É um estilo no qual um sistema é dividido em serviços pequenos, independentes e implantáveis de forma autônoma. Cada microsserviço implementa uma função de negócio específica, possui seu próprio banco de dados e se comunica com outros por meio de APIs.

Permite entregas contínuas, escalabilidade independente e maior autonomia das equipes. Reduzindo o acoplamento entre partes do sistema.

Muito utilizado quando o sistema é grande e tende a crescer mais. A arquitetura de microsserviços vai estrangulando a funcionalidade do sistema antigo.

# das-1-2025-2-a

--------------------------------------------------------------------------------------- 04/08/2025 --------------------------------------------------------------------------------------------
PRINCÍPIOS DE PROJETO DE CÓDIGO
Princípios de projeto de código são diretrizes e boas práticas que orientam os desenvolvedores na criação de software de alta qualidade, visando tornar o código mais legível, compreensível, manutenível e eficiente.

PADRONIZAÇÃO DE CÓDIGO
Os padrões ajudam a reduzir a complexidade dos sistemas, tornando-os mais fáceis de entender, manter e evoluir

OCULTAMENTO DE INFORMAÇÃO
Não é preciso conhecer em detalhe todo o funcionamento de um framework para utilizá-lo. Apenas a interface essencial deve estar visível, escondendo a complexidade interna.

COESÃO
O código que tem coesão, é um código que faz uma coisa bem feita. Se espera que um código seja escrito com coesidade. Ao verificar o código o programador reconheça do que se trata com facilidade. Elementos de um módulo (como classes, funções ou pacotes) estão relacionados e trabalham juntos para um propósito único e bem definido.

ACOPLAMENTO: dependência de uma classe com outra
Autoacoplamento: instanciação e uso de um método no construtor de outra classe

ABSTRAÇÃO
Capacidade de abstrair informações do mundo real diminuindo a complexidade do sistema, que são representações simplificadas de entidades

DÉBITO TÉCNICO
Problemas técnicos no código, algo que mexido entrará em colapso

HERANÇA
Permite que uma classe (subclasse) herde propriedades (atributos e métodos) de outra classe (superclasse), promovendo a reutilização de código e a criação de hierarquias de classes.

IMPLENTAÇÃO
É a fase em que um software é instalado, configurado e adaptado para uso numa organização, transformando os dados técnicos em um sistema pronto para o utilizador final 

Código de associação  - auto acoplamento (quando mexo em uma parte do código e afeta outro)
class A {
   private B b;
}

--------------------------------------------------------------------------------------- 05/08/2025 --------------------------------------------------------------------------------------------

05/08/2025

package br.univille;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JOptionPane;

import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;


public class Janelinha extends JFrame{

    private JButton botaozinho;
    private Controlador controlador;

    public Janelinha() {
        setTitle("Eu nao acredito");
        setSize(500,500);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        botaozinho = new JButton("ME CLICA");
        controlador = new Controlador();
        botaozinho.addActionListener(controlador);

        /*botaozinho.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                JOptionPane.showMessageDialog(null,"oi");
            }
        });*/
        
        add(botaozinho);

        setVisible(true);
    }
    public static void main(String[] args) {
        new Janelinha();
    }
}

package br.univille;

import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.JOptionPane;

public class Controlador implements ActionListener{

    @Override
    public void actionPerformed(ActionEvent e) {
        meClica();
    }

    private void meClica(){
        JOptionPane.showMessageDialog(null, "NAO ACREDITO");
    }
    
    
}

SOLID - 5 CONCEITOS
Usar a orientação a objeto do jeito mais correto possível

S - SINGLE RESPONSABILITY PRINCIPLE
(principio de responsabilidade única) - toda classe deve ter uma única responsabilidade;

O - OPEN/CLOSED PRINCIPLE
(Princípio Aberto/Fechado) - uma classe deve estar fechada para modificações e aberta para extensões.

Prefira Composição a Herança - Evitar o útilizo de heranças, priorizar o utilizado de composição. Utilizar herança em casos de divisão. (Ex: gato <= animal => cachorro), o gato é um animal, mas nunca será um cachorro, mesma coisa o cachorro, o mesmo é um animal, mas nunca será um gato. "Herança expõe para subclasses detalhes de implementação das classes pai. Logo, frequentemente diz-se que herança viola o encapsulamento das classes pai."

O Princípio de Demeter - Princípio do Menor Conhecimento - (Principle of Least Knowledge) — defende que a implementação de um método deve invocar apenas os seguintes outros métodos:
- de sua própria classe (caso 1)
- de objetos passados como parâmetros (caso 2)
- de objetos criados pelo próprio método (caso 3)
- de atributos da classe do método (caso 4)
Limitar o objeto a atributos locais, evitando variáveis globais. 

L - LISKOV SUBSTITUTION PRINCIPLE
Princípio de Substituição de Liskov - Respeitar a assinatura do pai, trocar um filho pelo outro mantém a funcionalidade do código. 

I - INTERFACE SEGREGATION PRINCIPLE
Princípio da Segregação de Interfaces - a comunicação entre duas classes não deve ser feita diretamente, o ideal é essa comunicação de classe A e classe B é ser feita por uma interface;

D - DEPENDENCY INVERSION PRINCIPLE
(Principio de inversão de dependencia) - uma classe deve estabelecer dependências prioritariamente com abstrações e não com implementações concretas. (Controller => <<interface>> => Service). Não depende diretamente de uma classe e sim de uma interface 

MVC
M - Model (Representação dos dados)
V - HTML (interface/ tela)
C - Controlador (controlar a tela / ações dos botões)

O MVC (Model–View–Controller) é um padrão de arquitetura de software que separa responsabilidades em três camadas:

- Model (Modelo): Representa os dados e as regras de negócio do sistema. É responsável por manipular, armazenar e gerenciar as informações.
- View (Visão): É a interface com o usuário. Exibe os dados do modelo e recebe as interações do usuário.
- Controller (Controlador): Atua como intermediário entre Model e View. Recebe as ações do usuário (cliques, entradas, comandos), processa a lógica e atualiza o modelo ou a visão conforme necessário.

--------------------------------------------------------------------------------------- 11/08/2025 -----------------------------------------------------------------------------------------------------------------

CONTINUAÇÃO SOLID

--------------------------------------------------------------------------------------- 12/08/2025 -----------------------------------------------------------------------------------------------------------------

CONTINUAÇÃO SOLID

--------------------------------------------------------------------------------------- 25/08/2025 -----------------------------------------------------------------------------------------------------------------

OBSERVER
Observer é um padrão de design comportamental que permite definir um mecanismo de assinatura para notificar vários objetos sobre quaisquer eventos que aconteçam com o objeto que eles estão observando.

--------------------------------------------------------------------------------------- 26/08/2025 ----------------------------------------------------------------------------------------------------------------

FUNDAMENTOS DA ARQUITETURA DE SOFTWARE
   
- Caracteristicas da Arquitetura = requisitos não funcionais

Disponibilidade - Sistema acessível e funcional quando necessário
Confiabilidade - Executa corretamente e de forma consistente
Segurança - Proteção contra acessos e ações não autorizadas (cada CPF vazado é no mínimo 50 mil de multa)
Testabilidade - Facilidade para verificar funcionamento e corrigir erros
Escalabilidade - Capacidade de crescer sem perder eficiência
Agilidade - Facilidade para adaptar-se a mudanças
Tolerância a falhas - Continua operando mesmo com falhas parciais
Elasticidade - Ajusta recursos conforme a demanda
Recuperabilidade - Restauração rápida após falhas
Desempenho - Rapidez e eficiência no processamento
Implementabilidade - Facilidade de construir e implantar
Capacidade de aprendizagem - Habilidade de evoluir e melhorar com uso e dados
   
   *É impossível um sistema atender todas as caracnteristicas da arquitetura, sempre ficará alguma coisa pendente*

- Supply chain - utilização de bliblioteca abertas não confiáveis
  
DECISÕES DA ARQUITETURA
São regras que precisam ser mantidas no sistema, para que o mesmo tenha o mínimo de padronização. exemplo: iremos utilizar arquitetura baseada em camadas.

Decidir a esturutra do sistema, escolhendo a arquitetura, uma decisão importante, que poderá ter um custo alto se feito de qualquer jeito

  *A decisão da arquitetura depende das caracteristicas da arquitetura, um depende do outro*

PRINCÍPIOS DO DESIGN
Boas práticas, princípios que seria ideal sempre ser seguido

(arquitetura distribuida) - microsserviços - pequenas atividades bem feitas, cada microsserviço tem seu próprio banco de dados (cada um tem vida própria) 

SISTEMA DE MENSAGERIA
Serviço colocado no meio da arquitetura, que permite a troca de mensagens dos microsserviços, um manda mensagem e o outro recebe  

event driven architecture - arquitetura baseada em eventos (alexa - cria máquina virtual, responde a pergunta, e cai a máquina virtual)

--------------------------------------------------------------------------------------- 01/09/2025 --------------------------------------------------------------------------------------------

EXPECTATIVAS DO ARQUITETO

- Tomar decisões de arquitetura - decidir qual arquitetura/ estrutura será utilizada no sistema, utilizando sua experiência no mercado para orientar a sua equipe. "O segredo para tomar decisões arquiteturais eficientes é perguntar se a decisão da arquitetura está ajudando a orientar as equipes ao fazerem a escolha técnica certa ou se a decisão faz a escolha técnica por elas."
  
- Analisar continuamente a arquitetura - todo sistema muda com o tempo, com isso, é função do arquiteto analisar o sistema continuamente e atualizar de acorodo com a arquitetura do sistema. O famoso "não mexe, que está funcionando", não deve ser considerado, e sim tomar decições corretas de acordo com suas análises que facilitarão o sistema
  
- Manter-se atualizando com as últimas tendências - desenvolver software está cada vez mais complexo (Inteligência Artificial)
  
- Assegurar a conformidade com as decisões - o arquiteto verifica continuamente se as equipes de desenvolvimento seguem as decisões da arquitetura e os princípios do design definidos, documentados e comunicados por ele.
- Análise estática de código é a inspeção do código-fonte de um software sem executá-lo, utilizando ferramentas automatizadas para identificar bugs, vulnerabilidades de segurança e desvios de padrões de codificação antes da produção
   
- Exposição e experiência diverisades - um bom arquiteto já teve experiência em várias áreaa/funções e linguagens. Essencial ele ter conhecimento da regra de negócio do produto
  
- Ter conhecimento sobre o domínio do negócio - conhecer o negócio do cliente, por exemplo, o arquiteto não precisa ser especialista em finanças, mas precisa conhecer os termos utilizadados em finanças para poder entender a demanda do cliente.
  
- Ter habilidades interpessoais - um arquiteto precisa ser um gestor tambémm, um líder da equipe, incetivando e extaindo o melhor de cada membro da equipe

- Enteder e lidar bem com questões políticas - fundamental negociar com o cliente, negociar mais prazos, funcionalidades, influenciar e proteger sua equipe

DEADLOCK - (ou interbloqueio) 
É uma situação de impasse em computação onde dois ou mais processos ficam permanentemente bloqueados, cada um esperando que o outro libere um recurso que ele precisa para continuar sua execução. Isso cria uma espera circular, onde o Processo A espera por um recurso do Processo B, e o Processo B espera por um recurso do Processo A, impedindo que qualquer um deles avance. 

OPERAÇÕES - DevOps
uma maneira de entregar valor ao meu cliente mais rápido
metodologia que vai melhorando cada vez mais

--------------------------------------------------------------------------------------- 02/09/2025 --------------------------------------------------------------------------------------------

DIFERENÇA ENTRE ARQUITETURA E DESIGN
A arquitetura de software define a estrutura global e os componentes principais de um sistema, ou seja, o que terá no sistema, enquanto o design se concentra nos detalhes de implementação desses componentes e suas interações em um nível mais baixo, ou seja, como será implementado as decisões tomada pelo arquiteto. A arquitetura é uma visão de alto nível que garante requisitos globais como escalabilidade e segurança, enquanto o design detalha como cada parte do sistema funciona e se comunica. 

Como é a formação do conhecimento de um arquiteto modelo T?
Uma formação ampla, não se concentra em apenas uma linguagem ou área específica de trabalho. O arquieto tem a capacidade de resolver o mesmo problema, utilizando meios diferentes.

--------------------------------------------------------------------------------------- 08/09/2025 --------------------------------------------------------------------------------------------

Pensamento Arquitetônico: Trade-Offs - Compensação. (perco de uma parte, mas ganho em outra)

Toda arquitetura nunca atendederá todos os requisitos, não há uma solução ideal que resolva todos os problemas, existem compensações / meio termos.

database centric - um banco de dados entre o insert e o select

publisher => subscribers
Um para muitos, quando o publisher publica no tópico, todos os inscritos (subscribers) recebem as mensagens

Push notification = tópicos

Todos os assinantes recebem a mensagem do publicante

stream - permite voltar no tempo e reprocessar as mensagens. O stream possui um conceito dentro de si chamados partitions ou sharding (uma janela de tempo de 24horas a 7 dias)

RabbitMQ - Broker de mensagens para filas e roteamento
AWS SNS - Serviço de notificação/publish-subscribe da AWS
Azure Service Bus - Mensageria corporativa com filas e tópicos
Google Pub/Sub - Mensageria assíncrona e escalável do Google Cloud
Redis - Banco em memória, rápido, usado para cache e filas

PROTOCÓLOS:
AMQP - Protocolo de mensageria avançada, confiável e robusto para filas
MQTT - Protocolo leve de publicação/assinatura, ideal para IoT
WebSocket - Comunicação bidirecional em tempo real sobre TCP

Enqueue - Inserir um item na fila (entrar)
Dequeue - Remover um item da fila (sair)

SENDER
É o componente que envia dados ou mensagens para outro sistema, serviço ou receptor

RECEIVER 
É o componente que recebe dados ou mensagens em um sistema de comunicação ou mensageria

BUFFER
Área temporária de memória usada para armazenar dados enquanto são transferidos entre sistemas, dispositivos ou processos.

POOLING
Buscar as mensagens na fila (caixa de correios de casa, todos os dias verificar se tem cartas)

AWS SQS - Fila de mensagens totalmente gerenciada da AWS, simples e escalável.
Azure Service Bus - Serviço de mensageria corporativa da Azure, com suporte a filas, tópicos e padrões avançados.
RabbitMQ - Broker de mensagens open source, flexível, suporta vários protocolos (como AMQP

Se um receiver cair, as mensagens ficarão na fila, e quando ele voltar terá acesso a essas mensagens

Quando incluirmos alguém no tópico, não muda nada no publisher, pois o publisher e o subscribers estão totalmente desacoplados

Quando incluirmos alguém na fila, precisamos mudar o publisher também, criar um novo caminho de comunicação 

Tudo depende, depende do tamanho da mensagem, quantas mensagens, o tópico não é melhor que a fila, e nem a fila é melhor que o tópico, tudo depende de qual é a aplicação.

"Com essa análise, fica claro que a abordagem de tópico usando o modelo de mensageria para publicar e assinar é a escolha óbvia e melhor. Contudo, para citar Rich Hickey, o criador da linguagem de programação Clojure:

 "Os programadores conhecem os benefícios de tudo e os trade-offs de nada. Os arquitetos precisam entender ambos."

ARQUITETURA FAN-OUT
É um padrão de mensageria onde uma mensagem publicada por um produtor é replicada e entregue a múltiplos consumidores ao mesmo tempo.
Exemplo:
O sender envia a mensagem para um tópico ou exchange.
O sistema distribui (faz o fan-out) para todas as filas ou subscribers conectados.
Cada consumidor recebe sua cópia da mensagem.

------------------------------------------------------------------------------- 29/09/2025 - 2ª BIMESTRE --------------------------------------------------------------------------------------------
https://learn.microsoft.com/pt-br/azure/architecture/patterns/circuit-breaker?wt.mc_id=AZ-MVP-5003638

CIRCUIT BREAKER
O padrão Circuit Breaker ajuda a lidar com falhas que podem levar diferentes períodos de tempo para serem resolvidas quando um aplicativo se conecta a um serviço ou recurso remoto. Um disjuntor bloqueia temporariamente o acesso a um serviço com falha depois de detectar falhas. Essa ação impede repetidas tentativas malsucedidas para que o sistema possa se recuperar efetivamente. Esse padrão pode melhorar a estabilidade e a resiliência de um aplicativo.

Quando um sistema (A) chama o outro (B), porém não confio se o segundo sistema esteja no ar

A idéia é protejer o sistema, como se fosse um disjuntor

Estados de um circuit Breaker
Closed - Quando está tudo bem o circuit Breaker está tudo fechado (closed)
Open - Quando acontece uma falha, o disjuntor (circuit Breaker), abre, ou seja, aconteceu uma falha, chamei o sistema B, mas ele não respondeu
Half-Open - sistema tenta conectar, como se fosse um rele térmico, ele tenta ligar se o rele ainda estiver quente ele não fecha o circuit breaker, se o rele estiver pronto pra ligar, ele liga, porem o sistema fica em alerta, necessita atenção

------------------------------------------------------------------------------- 06/10/2025 - 2ª BIMESTRE --------------------------------------------------------------------------------------------

Definição das características da arquitetura
- Devem ser:
  * Fora do domínio do problema.
  * Influenciar a estrutura do design.
  * Essenciais para o sucesso da aplicação.
- Direcionam decisões arquiteturais.
- Impactam diretamente a qualidade e viabilidade do sistema.

Categorias de Características da Arquitetura
- Operacionais:
  * Disponibilidade            * Tempo que o sistema deve ficar ativo.
  * Desempenho                 * Tempo de resposta, testes de estresse, picos.
  * Escalabilidade             * Suportar aumento de usuários/dados.
  * Confiabilidade             * Funcionar mesmo sob falhas.
  * Recuperabilidade           * Tempo de recuperação após falha.
  * Robustez                   * Lidar com erros e falhas externas.
- Estruturais:
  * Manutenção                 * Facilidade de alteração/melhoria.
  * Portabilidade              * Rodar em diferentes plataformas.
  * Reutilização               * Uso de componentes em outros projetos.
  * Atualização                * Facilidade de atualizar versões.
  * Instalação                 * Facilidade de instalar em diferentes ambientes.
- Transversais:
  * Segurança                  * Criptografia, controle de acesso.
  * Privacidade                * Proteção contra acessos internos indevidos.
  * Autenticação e Autorização * Identificar e limitar acesso.
  * Acessibilidade             * Inclusão de usuários com deficiência.
  * Legalidade                 * Conformidade com leis e regulamentos.
  * Usabilidade                * Facilidade de uso e aprendizado.
  * Armazenamento              * Políticas de retenção de dados.

Características Explícitas vs. Implícitas
- Explícitas:
  * Aparecem nos requisitos.
- Implícitas:
  * São essenciais, mas raramente documentadas.

Definições ISO
- Eficiência do desempenho:
  * Recursos vs. resposta.
- Compatibilidade:
  * Integração com outros sistemas.
- Confiabilidade:
  * Estabilidade e tolerância a falhas.
- Segurança:
  * Proteção dos dados e rastreabilidade.
- Manutenibilidade:
  * Facilidade de modificar e testar.
- Portabilidade:
  * Adaptação a diferentes ambientes.
- Usabilidade:
  * Facilidade de uso e acessibilidade.

------------------------------------------------------------------------------- 07/10/2025 - 2ª BIMESTRE --------------------------------------------------------------------------------------------
https://learn.microsoft.com/pt-br/azure/architecture/patterns/cqrs

CQRS
(Segregação de Responsabilidade de Comando e Consulta) é um padrão de design que segrega operações de leitura e gravação de um armazenamento de dados em modelos de dados separados. Essa abordagem permite que cada modelo seja otimizado de forma independente e pode melhorar o desempenho, a escalabilidade e a segurança de um aplicativo.

Usado quando atinge o limite da escalabilidade vertical da máquina
Estância primária - Somente para escrever (servidor 1)
Replica de leitura - Somente para ler (servidor 2)
O sistema poderá estar conectado com 2,3 ou mais bancos de dados
Podendo ter atrasos, pois a comunicação entre os bancos é assincrona

------------------------------------------------------------------------------- 09/10/2025 - 2ª BIMESTRE --------------------------------------------------------------------------------------------
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

------------------------------------------------------------------------------- 10/10/2025 - 2ª BIMESTRE --------------------------------------------------------------------------------------------
https://learn.microsoft.com/pt-br/azure/architecture/patterns/retry

TRÊS CAMADAS
Uma arquitetura que ficou bem popular no final dos anos 1990 foi uma arquitetura de três camadas, que fornecia mais camadas de separação. Quando ferramentas como servidores de aplicação se tornaram populares em Java e .NET, as empresas começaram a criar ainda mais camadas na topologia: uma camada de banco de dados usando um servidor de banco de dados com capacidade industrial, uma camada de aplicação gerenciada por um servidor de aplicação, um front-end escrito em HTML gerado e cada vez mais JavaScript, conforme suas capacidades expandiam.

ARQUITETURAS MONOLÍTICAS VERSUS DISTRIBUÍDAS
Monolíto - sistema onde todas as funcionalidades estão em uma única base de código centralizado

LOG DISTRIBUÍDO
Um log distribuído é um registro de eventos ou mensagens mantido de forma consistente entre vários nós (máquinas) em um sistema distribuído. Ele funciona como uma sequência ordenada e imutável de registros que todos os participantes conseguem ler e seguir na mesma ordem.

TRANSAÇÕES DISTRIBUIDAS
Garante que todas as partes envolvidas em uma operação completem com sucesso ou todas sejam revertidas.

------------------------------------------------------------------------------- 20/10/2025 - 2ª BIMESTRE --------------------------------------------------------------------------------------------

A arquitetura em camadas é um dos estilos mais comuns no desenvolvimento de software devido à sua simplicidade, familiaridade e baixo custo. Ela organiza o sistema em níveis, cada um com responsabilidades específicas, normalmente divididos em apresentação, negócios, persistência e banco de dados. Esse formato reflete naturalmente a estrutura de muitas organizações, o que contribui para sua adoção.

Há dois modelos de comunicação entre camadas: o estrito, em que cada camada só acessa a imediatamente inferior, e o relaxado, que permite saltos entre camadas, oferecendo flexibilidade, mas podendo aumentar o acoplamento. Entre suas vantagens estão a clareza organizacional, a separação de responsabilidades e a facilidade de testes. No entanto, ela pode se tornar rígida, dificultar escalabilidade independente e não se encaixar bem em arquiteturas distribuídas ou orientadas a eventos. É mais adequada para sistemas tradicionais de CRUD e aplicações corporativas, mas menos indicada para cenários modernos que exigem reatividade e alta flexibilidade.

------------------------------------------------------------------------------- 27/10/2025 - 2ª BIMESTRE --------------------------------------------------------------------------------------------

PIPELINE
É uma sequência de etapas organizadas, onde cada etapa recebe uma entrada, processa algo e entrega a saída para a próxima etapa. É como uma “linha de montagem”, em que cada fase executa uma parte do trabalho até completar o resultado final. O mesmo é ideal para processamento contínuo, transformações em fluxo e tarefas que podem ser divididas em passos claros. Ele promove baixo acoplamento, alta coesão e reutilização de componentes.

------------------------------------------------------------------------------- 03/11/2025 - 2ª BIMESTRE --------------------------------------------------------------------------------------------

ARQUITETURA MICROKERNEL
A arquitetura Microkernel divide o sistema em um núcleo mínimo, que contém apenas as funções essenciais, e um conjunto de plugins, que adicionam ou estendem funcionalidades. O núcleo é estável e simples, os plugins são modulares, podem ser trocados e evoluem sem afetar o restante do sistema. Esse estilo é ideal para plataformas extensíveis, como IDEs e sistemas que precisam de personalização constante.







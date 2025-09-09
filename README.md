# das-1-2025-2-a

--------------------------------------------------------------------------------------- 04/08/2025 --------------------------------------------------------------------------------------------

*princípios de projeto de código
*padronização de código
*ocultamento de informação
*coesão
*Acoplamento

O que é Abstração:
Capacidade de abstrair informações do mundo real diminuindo a complexidade do sistema, que são representações simplificadas de entidades

Débito técnico, problemas técnicos no código, algo que mexido entrará em colapso

O código que tem coesão, é um código que faz uma coisa bem feita. Se espera que um código seja escrito com coesidade. Ao verificar o código o programador reconheça do que se trata com facilidade.

Herança
Implementação
Associação 

Código de associação  - auto acoplamento (quando mexo em uma parte do código e afeta outro)
class A {
   private B b;
}

---------------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------- 05/08/2025 --------------------------------------------------------------------------------------------

05/08/2025

Solid - 5 conceitos
Usar a orientação a objeto do jeito mais correto possível
S - Single Responsibility Principle (principio de responsabilidade única) - toda classe deve ter uma única responsabilidade;

O - Open/Closed Principle (Princípio Aberto/Fechado) - uma classe deve estar fechada para modificações e aberta para extensões.

Prefira Composição a Herança - Evitar o útilizo de heranças, priorizar o utilizado de composição. Utilizar herança em casos de divisão. (Ex: gato <= animal => cachorro), o gato é um animal, mas nunca será um cachorro, mesma coisa o cachorro, o mesmo é um animal, mas nunca será um gato. "Herança expõe para subclasses detalhes de implementação das classes pai. Logo, frequentemente diz-se que herança viola o encapsulamento das classes pai."

O Princípio de Demeter - Princípio do Menor Conhecimento - (Principle of Least Knowledge) — defende que a implementação de um método deve invocar apenas os seguintes outros métodos:
- de sua própria classe (caso 1)
- de objetos passados como parâmetros (caso 2)
- de objetos criados pelo próprio método (caso 3)
- de atributos da classe do método (caso 4)
Limitar o objeto a atributos locais, evitando variáveis globais. 

L - Liskov Substitution Principle (Princípio de Substituição de Liskov) - Respeitar a assinatura do pai, trocar um filho pelo outro mantém a funcionalidade do código. 

I - Interface Segregation Principle - (Princípio da Segregação de Interfaces) - a comunicação entre duas classes não deve ser feita diretamente, o ideal é essa comunicação de classe A e classe B é ser feita por uma interface;

D - Dependency Inversion Principle - (Principio de inversão de dependencia) - uma classe deve estabelecer dependências prioritariamente com abstrações e não com implementações concretas. (Controller => <<interface>> => Service). Não depende diretamente de uma classe e sim de uma interface 

MVC
M - Model (Representação dos dados)
V - HTML (interface/ tela)
C - Controlador (controlar a tela / ações dos botões)



11/08/2025
Continuação SOLID

--------------------------------------------------------------------------------------- 12/08/2025 --------------------------------------------------------------------------------------------

Continuação SOLID

26/08/2025
Fundamentos da Arquitetura de Software
   
- Caracteristicas da Arquitetura = requisitos não funcionais
   Disponibilidade - estar online por um tempo definido
   Confiabiliade - o sistema faz o que deve ser feito
   Segurança - quão seguro o sistema é (cada CPF vazado é no mínimo 50 mil de multa)
   Testabilidade
   Escalabildade
   Agilidade
   Tolerância a falhas
   Elasticidade
   Recuperabilidade
   Desempenho
   Implementabilidade
   Capacidade de aprendizagem
   
   *É impossível um sistema atender todas as caracnteristicas da arquitetura, sempre ficará alguma coisa pendente*

   Supply chain - utilização de bliblioteca abertas não confiáveis
  
- DECISÕES DA ARQUITETURA
   São regras que precisam ser mantidas no sistema, para que o mesmo tenha o mínimo de padronização. exemplo: iremos utilizar arquitetura baseada em camadas.

  Decidir a esturutra do sistema, escolhendo a arquitetura, uma decisão importante, que poderá ter um custo alto se feito de qualquer jeito

  *A decisão da arquitetura depende das caracteristicas da arquitetura, um depende do outro*

  
- PRINCÍPIOS DO DESIGN
Boas práticas, princípios que seria ideal sempre ser seguido

(arquitetura distribuida) - micro serviços - pequenas atividades bem feitas, cada micro serviço tem seu próprio banco de dados (cada um tem vida própria) 


sistema de mensageria - serviço colocado no meio da arquitetura, que permite a troca de mensagens dos micros serviços, um manda mensagem e o outro recebe  

event driven architecture - arquitetura baseada em eventos (alexa - cria máquina virtual, responde a pergunta, e cai a máquina virtual)

--------------------------------------------------------------------------------------- 01/09/2025 --------------------------------------------------------------------------------------------

EXPECTATIVAS DO ARQUITETO

- Tomar decisões de arquitetura - decidir qual arquitetura/ estrutura será utilizada no sistema, utilizando sua experiência no mercado para orientar a sua equipe. "O segredo para tomar decisões arquiteturais eficientes é perguntar se a decisão da arquitetura está ajudando a orientar as equipes ao fazerem a escolha técnica certa ou se a decisão faz a escolha técnica por elas."
  
- Analisar continuamente a arquitetura - todo sistema muda com o tempo, com isso, é função do arquiteto analisar o sistema continuamente e atualizar de acorodo com a arquitetura do sistema. O famoso "não mexe, que está funcionando", não deve ser considerado, e sim tomar decições corretas de acordo com suas análises que facilitarão o sistema
  
- Manter-se atualizando com as últimas tendências - desenvolver software está cada vez mais complexo (Inteligência Artificial)
  
- Assegurar a conformidade com as decisões - o arquiteto verifica continuamente se as equipes de desenvolvimento seguem as decisões da arquitetura e os princípios do design definidos, documentados e comunicados por ele.
- Análise estática de código é a inspeção do código-fonte de um software sem executá-lo, utilizando ferramentas automatizadas para identificar bugs, vulnerabilidades de segurança e desvios de padrões de codificação antes da produção
   
- Exposição e experiência diverisades - um bom arquiteto já teve experiência em várias áreaa/funções e linguagens. Essencial ele ter conhecimento da regra de negócio do produto
  
- Ter conhecimento sobre o domínio do negócio -
  
- Ter habilidades interpessoais - um arquiteto precisa ser um gestor tambémm, um líder da equipe, incetivando e extaindo o melhor de cada membro da equipe

- Enteder e lidarr bem com questões políticas - fundamental negociar com o cliente, negociar mais prazos, funcionalidades, influenciar e proteger sua equipe




- 

DEADLOCK - (ou interbloqueio) é uma situação de impasse em computação onde dois ou mais processos ficam permanentemente bloqueados, cada um esperando que o outro libere um recurso que ele precisa para continuar sua execução. Isso cria uma espera circular, onde o Processo A espera por um recurso do Processo B, e o Processo B espera por um recurso do Processo A, impedindo que qualquer um deles avance. 

OPERAÇÕES - DevOps
uma maneira de entregar valor ao meu cliente mais rápido
metodologia que vai melhorando cada vez mais

--------------------------------------------------------------------------------------- 02/09/2025 --------------------------------------------------------------------------------------------

Resuma a diferença entre arquitetura e design ?
A arquitetura de software define a estrutura global e os componentes principais de um sistema, ou seja, o que terá no sistema, enquanto o design se concentra nos detalhes de implementação desses componentes e suas interações em um nível mais baixo, ou seja, como será implamentado as decisões tomada pelo arquiteto. A arquitetura é uma visão de alto nível que garante requisitos globais como escalabilidade e segurança, enquanto o design detalha como cada parte do sistema funciona e se comunica. 

Como é a formação do conhecimento de um arquiteto modelo T?
Uma formação ampla, não se concentra em apenas uma linguagem ou área específica de trabalho. O arquieto tem a capacidade de resolver o mesmo problema, utilizando meios diferentes.

--------------------------------------------------------------------------------------- 08/09/2025 --------------------------------------------------------------------------------------------
Pensamento Arquitetônico: Trade-Offs - Compensação.

Toda arquitetura nunca atendederá todos os requisitos, não há uma solução ideal que resolva todos os problemas, existem compensações / meio termos.

database centric - um banco de dados entre o insert e o select

publisher => subscribers
Um para muitos, quando o publisher publica no tópico, todos os inscritos (subscribers) recebem as mensagens

Push notification = tópicos

Todos os assinantes recebem a mensagem do publicante

stream - permite voltar no tempo e reprocessar as mensagens. O stream possui um conceito dentro de si chamados partitions ou sharding (uma janela de tempo de 24horas a 7 dias)

rabbitmq
aws sns
azure servicebus
google pubsug
redis

protocolos:
amqp
mqtt
web socket

enqueue dequeue

sender (1 para 1)
receiver

buffer 

pooling - buscar as mensagens na fila(caixa de correios de casa , todos os dias verificar se tem cartas)

aws sqs
azure service bus
rabbitmq

Se um receiver cair, as mensagens ficarão na fila, e quando ele voltar terá acesso a essas mensagens

Quando incluirmos alguém no tópico, não muda nada no publisher, pois o publisher e o subscribers estão totalmente desacoplados

Quando incluirmos alguém na fila, precisamos mudar o publisher também, criar um novo caminho de comunicação 

Tudo depende, depende do tamanho da mensagem, quantas mensagens, o tópico não é melhor que a fila, e nem a fila é melhor que o tópico, tudo depende de qual é a aplicação.


"Com essa análise, fica claro que a abordagem de tópico usando o modelo de mensageria para publicar e assinar é a escolha óbvia e melhor. Contudo, para citar Rich Hickey, o criador da linguagem de programação Clojure:

Os programadores conhecem os benefícios de tudo e os trade-offs de nada. Os arquitetos precisam entender ambos."

arquitetura fan-out












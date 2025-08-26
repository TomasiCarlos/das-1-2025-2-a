# das-1-2025-2-a

04/08/2025

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

12/08/2025
Continuação SOLID

26/08/2025
Fundamentos da Arquitetura de Software
   
- Caracteristicas da Arquitetura
   Disponibilidade - estar online por um tempo definido
   Confiabiliade - o sistema faz o que deve ser feito
   Segurança - quão seguro o sistema é (cada CPF vazado é no mínimo 50 mil de multa)
   


   Supply chain - utilização de bliblioteca abertas não confiáveis
  
- Decisões da Arquitetura
   São regras que precisam ser mantidas no sistema, para que o mesmo tenha o mínimo de padronização. exemplo: iremos utilizar arquitetura baseada em camadas.
  

  
- Príncipios do Design
Boas práticas, princípios que seria ideal sempre ser seguido

sistema de mensageria - serviço colocado no meio da arquitetura, que permite a troca de mensagem, um manda mensagem e o outro recebe  

event driven architecture - arquitetura baseada em eventos (alexa - cria máquina virtual, responde a pergunta, e cai a máquina virtual)








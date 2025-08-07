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
S - Single Responsibility Principle (principio de responsabilidade única) - toda classe deve ter uma única responsabilidade.
O - Open/Closed Principle (Princípio da Segregação de Interfaces) - a comunicação entre duas classes não deve ser feita diretamente, o ideal é essa comunicação de classe A e classe B é ser feita por uma interface
L - Liskov Substitution Principle () - 
I - Interface Segregation Principle
D - Dependency Inversion Principle

MVC
M - Model (Representação dos dados)
V - HTML (interface/ tela)
C - Controlador (controlar a tela / ações dos botões)

package br.univille;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JOptionPane;

import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.MouseEvent;
import java.awt.event.MouseMotionListener;

public class Janelinha extends JFrame 
            implements ActionListener, MouseMotionListener{

    private JButton botaozinho;

    public Janelinha() {
        setTitle("Eu nao acredito");
        setSize(500,500);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        botaozinho = new JButton("ME CLICA");
        botaozinho.addActionListener(this);
        botaozinho.addMouseMotionListener(this);
        add(botaozinho);

        setVisible(true);
    }
    public static void main(String[] args) {
        new Janelinha();
    }

    private void meClica(){
        JOptionPane.showMessageDialog(null, "NAO ACREDITO");
    }
    @Override
    public void actionPerformed(ActionEvent e) {
        meClica();
    }
    @Override
    public void mouseDragged(MouseEvent e) {
        // TODO Auto-generated method stub
        throw new UnsupportedOperationException("Unimplemented method 'mouseDragged'");
    }
    @Override
    public void mouseMoved(MouseEvent e) {
        System.out.println("passou...");
    }


}


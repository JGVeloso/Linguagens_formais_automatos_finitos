## 1 - Resumo do Tema
Título: Chatbot de que tira dúvidas sobre tipos de variáveis
Objetivo: Tirar dúvidas sobre variáveis em diversas linguagens de programação com simplicidade e facilidade.

## 2 - Diagramas de estado

<img width="1230" height="1537" alt="Diagrama em branco" src="https://github.com/user-attachments/assets/0de7fcc0-46e2-4965-9430-69f340963db9" />

## 3) Tabela de Estados e Transições

| Estado | Ação do Usuário | Próximo Estado |
|--------|-----------------|----------------|
| SAUDACAO | Qualquer saudação | Escolha a linguagem de programação |
| Escolha a linguagem de programação | Escolher a linguagem | Escolha o tipo variável que quer saber sobre |
| Escolha o tipo variável que quer saber sobre | Escolher a variável | Escolher se deseja outra variável, linguagem ou finalizar |

Caminho 1 - Outra variável
| Estado | Ação do Usuário | Próximo Estado |
|--------|-----------------|----------------|
| Escolher se deseja outra variável, linguagem ou finalizar | Escolheu outra variável |Escolher se deseja outra variável, linguagem ou finalizar|
| Escolher se deseja outra variável, linguagem ou finalizar| Finalizou | Fim |
| Fim |
 
Caminho 2 - Outra linguagem 
| Estado | Ação do Usuário | Próximo Estado |
|--------|-----------------|----------------|
| Escolher se deseja outra variável, linguagem ou finalizar | Escolheu outra Linguagem |Escolha o tipo variável que quer saber sobre|
| Escolha o tipo variável que quer saber sobre | Escolher a variável | Escolher se deseja outra variável, linguagem ou finalizar |
| Escolher se deseja outra variável ou linguagem | Não escolheu nenhuma das opçoes | Fim |
| Fim |

Caminho 3 - Finalizou
| Estado | Ação do Usuário | Próximo Estado |
|--------|-----------------|----------------|
| Escolher se deseja outra variável, linguagem ou finalizar | Escolheu finalizar | Fim |
| Fim |

## 4) Exemplo de Diálogo

**Usuário:** “Olá, boa noite.”  

**Bot:** “Olá, bem vindo ao chatbot sobre variáveis, qual linguagem de programação deseja saber:”

**Bot:** "Escolha a linguagem:
1 - Python
2 - Java
3 - C"

**Usuário:** “1”  

**Bot:**  "Escolha o tipo:
1 - int
2 - float
3 - string
4 - bool"  

**Usuário:** 4  

**Bot:** “Em Python, float representa números decimais. Ex: x = 3.14"

**Bot:**"O que deseja fazer agora?
1 - Aprender outro tipo
2 - Trocar de linguagem
3 - Sair"

**Usuário:** “3”

**Bot:** "Obrigado por usar nossos serviços, volte sempre!"

## 5) Código

```java
  import java.util.Scanner;
  
  public class ChatbotVariaveis {
  
    public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);
  
      String estado = "SAUDACAO";
      String linguagem = "";
      String tipo = "";
  
      while (!estado.equals("FIM")) {
  
        switch (estado) {
  
          case "SAUDACAO":
            System.out.println("Olá, bem-vindo ao chatbot sobre variáveis!\n");
            estado = "ESCOLHA_LINGUAGEM";
            break;
  
          case "ESCOLHA_LINGUAGEM":
            while (true) {
              System.out.println("Escolha a linguagem de programação:\n");
              System.out.println("1 - Python  \n2 - Java  \n3 - C");
              String langInput = sc.nextLine().trim();
  
              if (langInput.equals("1")) {
                linguagem = "Python";
                estado = "ESCOLHA_TIPO";
                break;
              } else if (langInput.equals("2")) {
                linguagem = "Java";
                estado = "ESCOLHA_TIPO";
                break;
              } else if (langInput.equals("3")) {
                linguagem = "C";
                estado = "ESCOLHA_TIPO";
                break;
              } else {
                System.out.println("Opção inválida. Digite 1, 2 ou 3.");
              }
            }
            break;
  
          case "ESCOLHA_TIPO":
            while (true) {
              System.out.println("Escolha o tipo de variável:\n");
              System.out.println("1 - int  \n2 - float/double  \n3 - string/char  \n4 - boolean");
              String tipoInput = sc.nextLine().trim();
  
              if (tipoInput.equals("1")) {
                tipo = "int";
              } else if (tipoInput.equals("2")) {
                tipo = linguagem.equals("Java") ? "double" : "float";
              } else if (tipoInput.equals("3")) {
                tipo = linguagem.equals("C") ? "char[]" : "String";
              } else if (tipoInput.equals("4")) {
                tipo = "boolean";
              } else {
                System.out.println("Opção inválida. Digite 1, 2, 3 ou 4.");
                continue; // permanece no mesmo estado
              }
  
              System.out.println("Em " + linguagem + ", " + tipo + " representa " + descricaoTipo(linguagem, tipo));
              estado = "ESCOLHER_OUTRA";
              break;
            }
            break;
  
          case "ESCOLHER_OUTRA":
            while (true) {
              System.out.println("O que deseja fazer agora?\n");
              System.out.println("1 - Aprender outro tipo  \n2 - Trocar de linguagem  \n3 - Sair");
              String escolha = sc.nextLine().trim();
  
              if (escolha.equals("1")) {
                estado = "ESCOLHA_TIPO";
                break;
              } else if (escolha.equals("2")) {
                estado = "ESCOLHA_LINGUAGEM";
                break;
              } else if (escolha.equals("3")) {
                estado = "FIM";
                break;
              } else {
                System.out.println("Opção inválida. Digite 1, 2 ou 3.");
              }
            }
            break;
  
        }
      }
  
      System.out.println("\nObrigado por usar nossos serviços, volte sempre!");
      sc.close();
    }
  
    public static String descricaoTipo(String linguagem, String tipo) {
      switch (tipo) {
        case "int":
          return "números inteiros. Ex: x = 10";
        case "float":
          return "números decimais. Ex: x = 3.14";
        case "double":
          return "números decimais de precisão dupla. Ex: x = 3.14";
        case "String":
          return "textos. Ex: nome = \"João\"";
        case "char[]":
          return "textos ou caracteres. Ex: char nome[] = \"Joao\";";
        case "boolean":
          return "valores verdadeiros ou falsos. Ex: flag = true";
        default:
          return "";
      }
    }
  }
```
## 6) Testes
### Teste 1: Saudação e escolha da linguagem
   ![0](https://github.com/user-attachments/assets/6aacdb0d-48c2-4289-973c-2df70606cf8f)
   > O usuário inicia a conversa e o chatbot responde com uma saudação, apresentando o menu de linguagens disponíveis.

### Teste 2: Escolha do tipo de variável
   ![3](https://github.com/user-attachments/assets/ed44e543-991c-4003-a0eb-70ae08c97eb2)
   > Após selecionar a linguagem, o chatbot exibe os tipos de variáveis disponíveis para escolha.

### Teste 3: Trocando de linguagem
   ![4](https://github.com/user-attachments/assets/333d68ae-cca1-4015-98c2-3d2b209d774e)
   > Depois de apresentar a descrição do tipo de variável, o chatbot oferece a opção de trocar a linguagem de programação.

### Teste 4: Escolhendo uma nova linguagem
   ![5](https://github.com/user-attachments/assets/0ee82644-c208-44f7-8629-39d0511c9499)
   > O chatbot retorna ao menu de seleção de linguagens, permitindo que o usuário escolha uma nova linguagem para explorar.

### Teste 5: Encerramento
   ![7](https://github.com/user-attachments/assets/de1b1da6-bf0a-4822-bfdd-eefc81ee7f8e)
   > Ao término das interações, o chatbot apresenta ao usuário a opção de sair, finalizando a sessão caso seja escolhida.

## 7) Conclusão
  O desenvolvimento do chatbot para esclarecimento de dúvidas sobre tipos de variáveis demonstrou, na prática, como máquinas de estados podem ser aplicadas para organizar fluxos de conversação de forma simples, intuitiva e eficiente. Os diagramas, a tabela de transições e os testes realizados comprovam o correto funcionamento do chatbot, evidenciando que o sistema responde adequadamente a diferentes caminhos de interação. Além disso, o código implementado em Java reforça a aplicação prática do conceito, mostrando como um fluxo conversacional pode ser controlado por meio de estruturas condicionais e loops. No geral, o projeto cumpre o objetivo proposto: oferecer uma ferramenta simples e funcional para ajudar iniciantes em programação a entenderem os tipos de variáveis nas principais linguagens. Com isso, demonstra-se não apenas o valor didático do chatbot, mas também a importância do uso de máquinas de estados no desenvolvimento de sistemas interativos mais organizados, previsíveis e fáceis de manter.

Questões sobre o Processo de Compilação em Java
1 Qual é a principal diferença entre o processo de compilação em Java e o de linguagens C++?
    O C++ é uma linguagem que é compilada diretamente em código binario, que é especifico do hardware e SO. O java é compilada e interpretada, o código é compliado pelo Javac e é executado pelo JVM,
    que funciona como uma camada intermediária entre o SO e o programa.

2 Explique o que acontece em cada uma das três fases de análise do compilador javac: Análise Léxica, Análise Sintática e Análise Semântica.
    Analise Lexica: o compilador lê o código caractere por caractere e agrupa tokens, exemplo: varchar nome = Gabriel.
    analise sintatica: o compilador verifica se a sequencia de tokens segue as regras da estrutura da linguagem, exemplo: varchar = nome  Gabriel.
    analise semantica: compilador valida se o codigo está correto, com as variáveis corretas. Exemplo: int x = "Gabriel".
    
3 O que é o bytecode e qual é a sua principal função no processo de compilação do Java?
    O bytecode é uma representação intermediária do programa Java, gerada pelo compilador javac em arquivos .class. Ele não é código de máquina, mas sim instruções portáveis que a JVM pode interpretar ou
    compilar para a máquina real. Sua principal função é permitir que programas java rodem em qualquer computador que tenha um JVM instalada.
    
4 Qual é o papel da Máquina Virtual Java (JVM) na execução de um programa Java, e por que o arquivo ".class" não é executado diretamente pelo sistema operacional?
    A JVM, como explicada anteriormente, é usada para dar uma maior portabilidade aos programas em JAVA, permitindo uma facil e rapida configuração para rodar os aplicativos java. O .class não é compilado
    diretamente por conta do bytecode, que não é um programa nativo do SO.
    
5 O que é o compilador JIT e como ele melhora o desempenho dos programas em Java?
    O JIT é um compilador dentro da JVM que entra em ação durante a execução do programa. Ele converte trechos frequentemente usados do bytecode diretamente em código de máquina nativo, 
    armazenando-os em cache. Assim, esses trechos deixam de ser interpretados toda vez e passam a rodar diretamente pelo processador, melhorando significativamente o desempenho. É uma mistura
    entre a flexibilidade da interpretação e a eficiência da compilação nativa.


Questões sobre Linguagens Formais em Java
6 Qual é a aplicação mais comum e direta das linguagens formais em Java, e para que ela é utilizada?
    A aplicação mais comum é na definição da sintaxe da linguagem de programação e na construção de compiladores e interpretadores. Em Java, as linguagens formais são usadas para:
    Definir as regras da linguagem, validar a estrutura do programa durante a compilação.
    
7 No processo de compilação de um código Java, como as linguagens formais são usadas nas fases de Análise Léxica e Análise Sintática?
  Na liguagem Lexica, ela usa expressões regulares para identificar tokens no código.
  A sintatica, Usa gramáticas livres de contexto para verificar se a sequência de tokens respeita as regras da linguagem.
  
8 O que é uma Máquina de Estado Finito (FSM) e como ela pode ser usada em Java?
  Uma Máquina de Estado Finito (FSM) é um modelo matemático que descreve um sistema que pode estar em um número finito de estados, mudando de um estado para outro
  com base em entradas. No java, ela pode ser usada para implementar analisadores léxicos que reconhecem os tokens, controlar fluxos de execução em jogos, protocolo de rede etc.
  
9 Como as linguagens formais se relacionam com os schemas de validação de documentos, como os usados para XML e JSON?
    XML e Json são baseados totalmente em linguagens formais, pois são modelos de dados usados em várias linguagens de programação e precisam seguir um padrão para isso.
    
10 De acordo com o texto, qual é a principal utilidade de ferramentas como o ANTLR no contexto de linguagens formais em Java?
  Ferramentas como o ANTLR (ANother Tool for Language Recognition), que podem ser usadas com Java, são geradores de parsers que automatizam a criação desses analisadores, permitindo que você defina a gramática
  de uma linguagem e o ANTLR gere o código Java para reconhecê-la.

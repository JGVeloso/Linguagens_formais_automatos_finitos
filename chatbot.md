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
| Escolha o tipo variável que quer saber sobre | Escolher a variável | Escolher se deseja outra variável ou linguagem |
| Escolher se deseja outra variável ou linguagem | Não escolheu nenhuma das opçoes | finaliza o atendimento |
| Fim |



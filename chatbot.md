stateDiagram-v2
    [*] --> SAUDACAO
    SAUDACAO --> ESCOLHER_SABOR: "quero/peça/pizza"
    ESCOLHER_SABOR --> ESCOLHER_TAMANHO: sabor selecionado
    ESCOLHER_TAMANHO --> ESCOLHER_BEBIDA: tamanho selecionado
    ESCOLHER_BEBIDA --> INFORMAR_ENDERECO: bebida selecionada ou "sem bebida"
    INFORMAR_ENDERECO --> CONFIRMAR: endereço recebido
    CONFIRMAR --> PAGAMENTO: confirmar pedido
    PAGAMENTO --> FINALIZADO: pagamento confirmado
    CONFIRMAR --> ESCOLHER_SABOR: "alterar"
    CONFIRMAR --> [*]: "cancelar"
    FINALIZADO --> [*]


CREATE TABLE PEDIDO_VENDA ( pedidovendaID INTEGER NOT NULL, cod_cliente NVARCHAR(160) NOT NULL, vendedorID INTEGER NOT NULL, cod_situacaoped NVARCHAR(160) NOT NULL, cod_forma_pagamento NVARCHAR(160) NOT NULL, CONSTRAINT PedidoVendas PRIMARY KEY (pedidovendaID), CONSTRAINT FK_vendedor CHAVE ESTRANGEIRA DE IDENTIFICAÇÃO (vendedorID) REFERENCES vendedor(vendedorID), CONSTRAINT FK_STTSPEDIDO FOREIGN KEY (cod_situacaoped) REFERENCES SITUACAO_PEDIDO(situacaopID), CONSTRAINT FK_FORMAPAG FOREIGN KEY (cod_forma_pagamento) REFERENCES FORMA_PAGAMENTO(formaPAGID), CONSTRAINT FK_CLIENTE FOREIGN KEY (cod _cliente) REFERÊNCIAS CLIENTE(clienteID) ); CREATE TABLE [vendedor] ( vendedorID INTEGER NOT NULL, telefone NVARCHAR(160) NOT NULL, endereco NVARCHAR(160) NOT NULL, nome NVARCHAR(160) NOT NULL, CONSTRAINT PRIMARY KEY (vendedorID) ); CREATE TABLE [FORMA_PAGAMENTO] ( [formaPAGID] INTEGER NOT NULL, [forma_pag] NVARCHAR(160) NOT NULL, CONSTRAINT [PAG] PRIMARY KEY ([formaPAGID]) ); CREATE TABLE [CLIENTE] ( [clienteID] INTEGER NOT NULL, [telefone] NVARCHAR(160) NOT NULL, [endereço] NVARCHAR(160) NOT NULL, [nome] NVARCHAR(160) NOT NULL, CONSTRAINT [cliente] PRIMARY KEY ( [clienteID]) ); CREATE TABLE [ITEM_PEDIDOVENDA] ( [itempedidovendaID] INTEGER NOT NULL, [pedidovendaID] NVARCHAR(160) NOT NULL, [cod_produto] NVARCHAR(160) NOT NULL, [qtd_item_pedido] NVARCHAR(160) NOT NULL, CONSTRAINT [ITEMPEDIDOVENDA] PRIMARY KEY ( [itempedidovendaID]), CONSTRAINT [FKPEDIDO_VENDA] FOREIGN KEY (pedidovendaID) REFERENCES PEDIDO_VENDA(pedidovendaID), CONSTRAINT [FKPRODUTO]
FOREIGN KEY (cod_produto) REFERENCES PRODUTO(cod_Produto) );
CREATE TABLE [PRODUTO] ( [cod_PRODUTO] INTEGER NOT NULL, [cod_TIPOPRODUTO] NVARCHAR(160) NOT NULL, [nome] NVARCHAR(160) NOT NULL, [vlr_produtoC] NVARCHAR(160) NOT NULL, [vlr_produtoV] NVARCHAR(160) NOT NULL, CONSTRAINT [PRODUTO] CHAVE PRIMÁRIA ([cod_Produto]), CONSTRAINT [FKcod_tipoP] CHAVE ESTRANGEIRA (cod_TIPOPRODUTO) REFERÊNCIAS TIPO_PRODUTO(cod_tipoP) ); CRIAR TABELA [ITEM_PEDIDOCOMPRA] ( [cod_itempedidoC] INTEGER NOT NULL, [cod_pedidocompra] NVARCHAR(160) NOT NULL, [cod_produto] NVARCHAR(160) NOT NULL, [QTD_itempedidoV] NVARCHAR(160) NOT NULL, CONSTRAINT [ITPCOMPRA] CHAVE PRIMÁRIA ( [cod_itempedidoC]), CONSTRAINT [FKPRODUTO] CHAVE ESTRANGEIRA (cod_produto) REFERÊNCIAS PRODUTO(cod_Produto), CONSTRAINT [FKPEDIDOCOMPRA] CHAVE ESTRANGEIRA (cod_pedidocompra) REFERÊNCIAS PEDIDO_COMPRA(cod_PEDIDOCOMPRA) ); 
CRIAR TABELA [PEDIDO_COMPRA] ( [cod_PEDIDOCOMPRA] INTEGER NOT NULL, [cod_FORNECEDOR] NVARCHAR(160) NOT NULL, [VLR_PEDIDO_COMPRA] NVARCHAR(160) NOT NULL, CONSTRAINT [PCOMPRA] CHAVE PRIMÁRIA ([cod_PEDIDOCOMPRA]) CONSTRAINT [FORNECEDORFK] CHAVE ESTRANGEIRA (cod_FORNECEDOR)REFERÊNCIAS FORNECEDOR(cod_fornecedor) );
CRIAR TABELA [COTAÇÃO] ( [cod_COTACAO] INTEGER NOT NULL, [cod_produto] NVARCHAR(160) NOT NULL, [cod_fornecedor] NVARCHAR(160) NOT NULL, [vlr_pedidoC] NVARCHAR(160) NOT NULL, CONSTRAINT [COTACAO] PRIMARY KEY ([cod_COTACAO]), CONSTRAINT [FKPRODUTO] FOREIGN KEY (cod_produto ) REFERÊNCIAS PRODUTO(cod_PRODUTO), CONSTRAINT [FORNECEDOR] CHAVE ESTRANGEIRA (cod_fornecedor) REFERÊNCIAS FORNECEDOR(cod_fornecedor) );
CREATE TABLE[TIPO_PRODUTO] ( [cod_tipoP] INTEGER NOT NULL, [descricao] NVARCHAR(160) NOT NULL, CONSTRAINT [TPRODUTO] PRIMARY KEY ([cod_tipoP]) );
CREATE TABLE [FORNECEDOR] ( [cod_fornecedor] INTEGER NOT NULL, [telefone] NVARCHAR(160) NOT NULL, [nome] NVARCHAR(160) NOT NULL, [endereço] NVARCHAR(160) NOT NULL, [e-mail] NVARCHAR(160) NÃO NULO,
CONSTRAINT [FORNECEDOR] CHAVE PRIMÁRIA ([cod_fornecedor]) ); 
CREATE TABLE [SITUACAO_PEDIDO] ( [situacaopID] inteiro NOT NULL, [STTS_PAG] NVARCHAR(160) NOT NULL, CONSTRAINT [CODSITUACAOP] CHAVE PRIMÁRIA ([situacaopID]) );
INSERT INTO CLIENTE (telefone, endereço, nome) VALUES ('111-1111', 'Rua das Flores, 123', 'Enzo'); 
INSERIR NO CLIENTE (telefone, endereço, nome) VALORES ('222-2222', 'Avenida dos Anjos, 456', 'Sophia'); 
INSERIR NO CLIENTE (telefone, endereço, nome) VALORES ('333-3333', 'Rua dos Amigos, 789', 'Miguel');
INSERT  INTK CLIENTE (telefone, endereço, nome) VALORES ('444-4444', 'Avenida da Paz, 012', 'Isabella');
INSERT INTO CLIENTE (telefone, endereço, nome) VALORES ('555-5555', 'Rua do Comércio, 789', 'Pedro'); INSERIR NO CLIENTE (telefone, endereço, nome) VALORES ('666-6666', 'Avenida da Prosperidade, 012', 'Larissa'); INSERIR NO CLIENTE (telefone, endereço, nome) VALORES ('777-7777', 'Rua das Estrelas, 345', 'Lucas'); INSERIR NO CLIENTE (telefone, endereço, nome) VALORES ('888-8888', 'Avenida da Alegria, 678', 'Julia');
INSERIT INTO CLIENTE (telefone, endereço, nome) VALORES ('999-9999', 'Rua do Sol, 901', 'Gabriel'); 
INSERT INTO CLIENT (telefone, endereço, nome) VALORES ('101-1010', 'Avenida da Lua, 234', 'Valentina');
INSERT INTO vendedor (telefone, endereco, nome) VALUES ('303-0303', 'Rua das Vendas, 111', 'Fernanda Oliveira' ); 
INSERT INTO vendedor (telefone, endereco, nome) VALUES ('404-0404', 'Avenida das Negociações, 222', 'Ricardo Santos');
INSERIR EM vendedor (telefone, endereco, nome) VALORES ('505-0505', 'Rua do Comércio, 333', 'Carolina Pereira'); INSERT INTO vendedor (telefone, endereco, nome) VALUES ('606-0606', 'Avenida do Empreendedor, 444', 'Renato Silva');
INSERIR EM vendedor (telefone, endereco, nome) VALORES ('707-0707', 'Rua das Oportunidades, 555', 'Fernando Costa'); 
INSERT INTO vendedor (telefone, endereco, nome) VALUES ('808-0808', 'Avenida das Vendas, 666', 'Amanda Almeida'); INSERT INTO vendedor (telefone, endereco, nome) VALUES ('909-0909', 'Rua dos Clientes, 777', 'Roberto Oliveira');
INSERT INTO vendedor (telefone, endereco, nome) VALUES ('101-0101', 'Avenida do Sucesso, 888', 'Patrícia Lima'); INSERT INTO vendedor (telefone, endereco, nome) VALUES ('111-1111', 'Rua do Progresso, 999', 'Gustavo Martins'); INSERT INTO vendedor (telefone, endereco, nome) VALUES ('121-2121', 'Avenida da Prosperidade, 1010', 'Camila Rodrigues');
INSERT INTO FORMA_PAGAMENTO VALUES (1, 'Cartão Visa'); INSERT INTO FORMA_PAGAMENTO VALUES (2, 'Boleto Bancário'); -- 
INSERT INTO PRODUTO VALUES (9, 'T1', 'Smartphone X', '800.00', '1000.00'); INSERIR NOS VALORES DO PRODUTO (10, 'T2', 'Mesa de Jantar Y', '200,00', '250,00');
INSERIR VALORES NO PRODUTO (11, 3, 'Smartphone X', '500,00', '800,00'); 
Inserções para tabela TIPO_PRODUTO INSERT INTO TIPO_PRODUTO VALUES (13, 'Eletrônicos'); INSERT INTO TIPO_PRODUTO VALUES (14, 'Móveis'); INSERT INTO TIPO_PRODUTO VALUES(17, 'CELULARES'); INSERT INTO TIPO_PRODUTO VALUES(18, 'ELETRODOMESTICOS'); INSERT INTO FORNECEDOR VALUES (19, '555-5555', 'Distribuidora ABC', 'Rua dos Fornecedores, 789', 'contato@abc.com' ); INSERIR NOS VALORES DO FORNECEDOR (20, '666-6666', 'Fábrica XYZ', 'Avenida da Indústria, 012', 'contato@xyz.com'); INSERIR VALORES NO PRODUTO (5, 18, 'smartphone ARAMUNI-Z PRO', '1200,00', '1800,00'); INSERIR NOS VALORES DO PRODUTO (4, 4, 'MICROONDAS', '7200,00', '9000,00'); -- ... Adicione mais inserções FORNECEDOR conforme necessário -- Inserções para tabela SITUACAO_PEDIDO INSERT INTO SITUACAO_PEDIDO VALUES (1, 'Aguardando Pagamento'); INSERT INTO SITUACAO_PEDIDO VALUES (2, 'Em Processamento'); -- ... Adicione mais inserções de SITUACAO_PEDIDO conforme necessário DELETE * produto delete * cliente DELETE FROM CLIENTE WHERE clienteID%2 SELECT PV.pedidovendaID, C.nome AS nome_cliente, V.nome AS nome_vendedor, SP.STTS_PAG AS situacao_pedido, FP.forma_pag AS forma_pagamento FROM PEDIDO_VENDA PV INNER JOIN CLIENTE C ON PV.cod_cliente = C.clienteID INNER JOIN vendedor V ON PV. vendedorID = V.vendedorID INNER JOIN SITUACAO_PEDIDO SP ON PV.cod_situacaoped = SP.situacaopID INNER JOIN FORMA_PAGAMENTO FP ON PV.cod_forma_pagamento = FP.formaPAGID; SELECT IPV.itempedidovendaID, PV.pedidovendaID, P.nome AS nome_produto, IPV.qtd_item_pedido FROM ITEM_PEDIDOVENDA IPV INNER JOIN PEDIDO_VENDA PV ON IPV.pedidovendaID = PV.pedidovendaID INNER JOIN PRODUTO P ON IPV.cod_produto = P.cod_PRODUTO; SELECT PC.cod_PEDIDOCOMPRA, F.nome AS nome_fornecedor, PC.VLR_PEDIDO_COMPRA FROM PEDIDO_COMPRA PC INNER JOIN FORNECEDOR F ON PC.cod_FORNECEDOR = F.cod_fornecedor; SELECT C.cod_COTACAO, P.nome AS nome_produto, F.nome AS nome_fornecedor, C.vlr_pedidoC FROM COTAÇÃO C INNER JOIN PRODUTO P ON C.cod_produto = P.cod_PRODUTO INNER JOIN FORNECEDOR F ON C.cod_fornecedor = F.cod_fornecedor; 

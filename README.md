DELETE — Comandos SQL
Objetivo

Utilizar o comando DELETE para excluir registros de tabelas de um banco de dados.

Atenção: algumas exclusões podem falhar devido a restrições de chave estrangeira (FOREIGN KEY), caso existam registros relacionados em outras tabelas.

1. Excluir cliente pelo ID
````
DELETE FROM cliente
WHERE id_cliente = 5;
````

Exclui o cliente cujo identificador é 5.

2. Excluir clientes por estado
````
DELETE FROM cliente
WHERE estado = 'SC';
````

Exclui todos os clientes cujo estado seja SC (Santa Catarina).

3. Excluir produtos pela marca
````
DELETE FROM produto
WHERE marca = 'LG';
````

Exclui todos os produtos cuja marca seja LG.

4. Excluir produtos por IDs específicos

````
DELETE FROM produto
WHERE id_produto IN (3, 5, 10);
````

Exclui os produtos cujos identificadores sejam 3, 5 ou 10.

Observação: para verificar vários valores, utiliza-se IN (...), e não vírgulas diretamente após o sinal de igualdade.

5. Excluir vendas sem desconto
sql
````
DELETE FROM venda
WHERE desconto_porcentual = 0.00;
````

Exclui todas as vendas cujo desconto percentual seja igual a zero.

6. Excluir vendas canceladas
sql
````
DELETE FROM venda
WHERE status_venda = 'Cancelada';
````

Exclui todas as vendas cujo status seja Cancelada.

Cuidados importantes
Execute um SELECT com a mesma condição antes de cada DELETE para conferir os registros que serão excluídos.
O comando DELETE sem WHERE exclui todos os registros da tabela.
Uma chave primária (PRIMARY KEY) ou única (UNIQUE) não impede, por si só, a exclusão de um registro.
Uma chave estrangeira (FOREIGN KEY) em outra tabela pode impedir a exclusão quando existem registros relacionados.
O comportamento depende das restrições configuradas, como RESTRICT, NO ACTION, CASCADE ou SET NULL.
Exemplo de verificação antes da exclusão
sql
SELECT *
FROM cliente
WHERE id_cliente = 5;


Confira o resultado antes de executar o DELETE.

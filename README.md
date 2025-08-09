Loja Roupas Online

Tema do Projeto
Banco de dados para loja virtual de roupas, gerenciando produtos, variantes, estoque e pedidos.

Descrição do Problema
Controlar o estoque, pedidos e informações de produtos e clientes de forma organizada e eficiente, evitando redundância e garantindo integridade.

Entidades e Relacionamentos
Categoria: Categoriza os produtos (ex: Camisetas, Calças).
Produto: Informações gerais do produto, ligado a uma categoria.
ProdutoVariante: Variante do produto, com cor, tamanho, SKU e estoque.
Pedido: Representa o pedido feito por um cliente.
PedidoItem: Itens dentro de um pedido, ligando variante e quantidade.
As tabelas são relacionadas com chaves estrangeiras garantindo integridade referencial.

Prints e Exemplos das Consultas
Exemplos de consultas realizadas:

-- Produtos mais vendidos
SELECT p.id_produto, p.nome, SUM(pi.quantidade) AS total_vendido
FROM PedidoItem pi
JOIN ProdutoVariante pv ON pi.id_variante = pv.id_variante
JOIN Produto p ON pv.id_produto = p.id_produto
GROUP BY p.id_produto, p.nome
ORDER BY total_vendido DESC
LIMIT 5;
<img width="893" height="391" alt="Captura de tela 2025-08-09 164956" src="https://github.com/user-attachments/assets/bfa451ca-5827-4644-8e9c-c565cbda58cf" />

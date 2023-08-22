# OutroExemploEmSQL

Aqui está outro projeto para estudos em SQL

# Esquema Lógico do Banco de Dados para uma Oficina:
Tabelas:
Cliente (cliente_id, nome, cpf, telefone)
Veiculo (veiculo_id, cliente_id, marca, modelo, ano)
Servico (servico_id, descricao, preco)
OrdemServico (ordem_id, veiculo_id, data_inicio, data_fim)
ItemServico (item_id, ordem_id, servico_id)

# Exemplos de queries SQL:
Recuperação simples com SELECT Statement:
SELECT * FROM Cliente;

Filtros com WHERE Statement:
SELECT descricao, preco FROM Servico WHERE preco > 100.00;

Expressões para gerar atributos derivados:
SELECT marca, modelo, CONCAT(marca, ' ', modelo) AS veiculo_completo FROM Veiculo;

Ordenação dos dados com ORDER BY:
SELECT nome, telefone FROM Cliente ORDER BY nome;

Condições de filtros aos grupos – HAVING Statement:
SELECT veiculo_id, COUNT(ordem_id) AS total_ordens
FROM OrdemServico
GROUP BY veiculo_id
HAVING COUNT(ordem_id) >= 2;

Junções entre tabelas para fornecer uma perspectiva mais complexa dos dados:
SELECT c.nome AS cliente, v.marca, v.modelo, o.data_inicio, o.data_fim
FROM Cliente c
JOIN Veiculo v ON c.cliente_id = v.cliente_id
JOIN OrdemServico o ON v.veiculo_id = o.veiculo_id;

# Esses exemplos de esquema lógico, script SQL e consultas SQL são apenas para fins de demonstração e você pode adaptá-los conforme necessário. 
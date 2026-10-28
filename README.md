# banco-de-dados-mysql-Sistema de Clientes
Sistema de Gestão de Clientes e Pedidos — Loja Fácil
1. Domínio do Banco de Dados

O projeto consiste no desenvolvimento de um banco de dados relacional para uma loja fictícia chamada Loja Fácil, com o objetivo de gerenciar clientes, produtos, pedidos e pagamentos.

O sistema foi desenvolvido utilizando MySQL e MySQL Workbench.

2. Contextualização

A Loja Fácil é uma empresa fictícia que comercializa produtos variados. Antes da implementação do banco de dados, as informações eram armazenadas em planilhas separadas, dificultando o controle e a organização dos dados.

Entre os principais problemas enfrentados estavam:

Duplicidade no cadastro de clientes.
Dificuldade para consultar pedidos e produtos vendidos.
Falta de integração entre pedidos e pagamentos.
Inconsistências nos valores das compras.
Dificuldade para gerar relatórios.
Risco de perda de informações.
3. Proposta de Melhoria

A proposta é implementar um Sistema Gerenciador de Banco de Dados Relacional (SGBD) utilizando MySQL.

A solução permite centralizar as informações, estabelecer relacionamentos entre tabelas, reduzir redundâncias e facilitar consultas e relatórios.

4. Modelagem Lógica do Banco de Dados

O banco de dados foi planejado para utilizar as seguintes entidades:

Clientes: armazena os dados dos clientes.
Produtos: registra os produtos comercializados.
Pedidos: registra as compras realizadas pelos clientes.
Itens do Pedido: relaciona os produtos aos pedidos e registra quantidade e preço unitário.
Pagamentos: registra os pagamentos relacionados aos pedidos.
Relacionamentos e cardinalidades
Clientes e Pedidos: um cliente pode realizar vários pedidos (1:N).
Pedidos e Itens do Pedido: um pedido pode conter vários itens (1:N).
Produtos e Itens do Pedido: um produto pode aparecer em vários itens de pedidos (1:N).
Pedidos e Pagamentos: um pedido pode possuir vários registros de pagamento (1:N).

O relacionamento entre Pedidos e Produtos é muitos para muitos (N:N), resolvido pela tabela associativa Itens do Pedido.

5. Formas Normais
Primeira Forma Normal (1FN)

Cada campo deve armazenar um único valor, sem listas de produtos ou múltiplos valores em uma mesma coluna.

Segunda Forma Normal (2FN)

Todos os atributos não-chave devem depender da chave primária completa. Na tabela associativa Itens do Pedido, os atributos referentes à quantidade e ao preço devem depender da identificação do item ou da combinação de pedido e produto, conforme a chave adotada.

Terceira Forma Normal (3FN)

Os atributos não-chave devem depender diretamente da chave primária, evitando dependências transitivas. Por exemplo, os dados do cliente ficam na tabela Clientes, em vez de serem repetidos em Pedidos.

Quarta Forma Normal (4FN)

A estrutura deve evitar dependências multivaloradas independentes. Caso um cliente possa possuir vários telefones e vários endereços, esses dados devem ser separados em tabelas próprias, evitando combinações redundantes.

6. Scripts SQL

O projeto contempla scripts para:

Criação do banco de dados.
Criação de todas as tabelas.
Definição de chaves primárias e estrangeiras.
Inserção de pelo menos cinco registros por tabela.
Execução de 15 consultas SQL contextualizadas.

As consultas devem demonstrar o uso de INNER JOIN, WHERE, LIKE, GROUP BY, ORDER BY, BETWEEN, SUM e outras funções e cláusulas SQL.

7. Consultas SQL

As consultas têm como objetivo responder questões relacionadas à gestão da loja, como:

Quais clientes realizaram pedidos?
Quais produtos estão cadastrados?
Quais pedidos foram realizados em determinado período?
Qual é o valor total dos pedidos?
Quais clientes realizaram mais compras?
Quais produtos aparecem com maior frequência nos pedidos?
Quais pagamentos estão associados a cada pedido?

Os resultados serão apresentados e conferidos após a execução dos scripts no MySQL Workbench.

8. Exportação do Banco de Dados (Dump)

Para exportar a estrutura e os dados do banco:

Abrir o MySQL Workbench.
Conectar-se à instância do MySQL.
Acessar Server → Data Export.
Selecionar o banco de dados do projeto.
Marcar as tabelas que serão exportadas.
Selecionar a opção de exportação da estrutura e dos dados.
Escolher a opção de exportação para arquivo SQL.
Definir o local de destino.
Clicar em Start Export.

O arquivo gerado poderá ser utilizado para recriar o banco de dados em outra instância MySQL.

9. Versionamento no GitHub

Os scripts SQL e a documentação do projeto serão armazenados neste repositório para facilitar a organização, o versionamento e a entrega acadêmica.

Os arquivos previstos são:

README.md — documentação do projeto.
estrutura_dados.sql — criação das tabelas e inserção dos registros.
consultas.sql — consultas SQL contextualizadas.
dump_loja_facil.sql — exportação completa do banco, quando gerada.

.
10. Tecnologias Utilizadas
MySQL
MySQL Workbench
SQL
GitHub
11. Conclusão

O projeto demonstra a aplicação dos conceitos de modelagem de dados, relacionamentos, cardinalidade, normalização e consultas SQL em um cenário empresarial fictício.

A implementação de um banco de dados relacional contribui para a organização, integridade e consistência das informações, facilitando a gestão de clientes, produtos, pedidos e pagamentos.

Observação: os scripts SQL e a modelagem devem ser incluídos no repositório após serem criados, executados e testados no MySQL Workbench.

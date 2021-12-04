### Bancos de Dados Relacionais (SQL) na AWS com Amazon RDS

<p align="justify">
    Explorando o Amazon RDS, um serviço de provisionamente e gerenciamento de banco de dados relacional na AWS.
    <br><br>
    O que é um banco de dados relacional?
    <br>
    Um banco de dados relacional é um mecanismo de armanezamento que permite a persistência de dados e opcionalmente implementar funcionalidades, armazenando os dados em tabelas, que possuem relacionamentos entre si.
    <br><br>
    Tabelas de um banco de dados relacional
    <br>
    São organizadas em colunas, onde cada coluna armazena um tipo de dados;
    <br>
    Os dados são armazenados em linhas da tabela;
    <br>
    Possuem uma chave primária (PK) que identificam de forma única cada registro de uma linha;
    <br>
    Possuem chaves estrangeiras (FK) que estabelecem o relacionamento entre tabelas; e
    <br>
    Utilizam índices para pesquisa rápida de dados.
    <br><br>
    Relacionamento entre tabelas em um banco de dados relacional
    <br>
    1:1 duas tabelas se relacionam de forma direta onde a chave primária de uma tabela é utilizada uma única vez em outra.
    <br>
    1:n duas tabelas se relacionam de forma direta onde a chave primária de uma tabela é utilizada várias vezes em outra.
    <br>
    n:n acontece de forma indireta entre duas tabelas, gerando de uma terceira tabela. Na prática ocorrem dois ou mais relacionamentos um para vários.
</p>
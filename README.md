### Bancos de Dados Relacionais (SQL) na AWS com Amazon RDS

<p align="justify">
    Explorando o Amazon RDS, um serviço de provisionamente e gerenciamento de banco de dados relacional na AWS.
    <br><br>
    <strong>O que é um banco de dados relacional?</strong>
    <br>
    Um banco de dados relacional é um mecanismo de armanezamento que permite a persistência de dados e opcionalmente implementar funcionalidades, armazenando os dados em tabelas, que possuem relacionamentos entre si.
    <br><br>
    <strong>Tabelas de um banco de dados relacional</strong>
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
    <strong>Relacionamento entre tabelas em um banco de dados relacional</strong>
    <br>
    1:1 duas tabelas se relacionam de forma direta onde a chave primária de uma tabela é utilizada uma única vez em outra.
    <br>
    1:n duas tabelas se relacionam de forma direta onde a chave primária de uma tabela é utilizada várias vezes em outra.
    <br>
    n:n acontece de forma indireta entre duas tabelas, gerando de uma terceira tabela. Na prática ocorrem dois ou mais relacionamentos um para vários.
    <br><br>
    <strong>Sobre o Amazon RDS</strong>
    <br>
    O Amazon Relational Database Service (Amazon RDS) facilita a configuração, a operação e a escalabilidade de bancos de dados relacionais na nuvem. Fornece capacidade econômica e redimensionável e automiza o provisionamento de hardware, configuração de bancos de dados, aplicação de patches e backups.
    <br><br>
    Mecanismos de banco de dados na Amazon RDS: Amazon Aurora, PostgreSQL, MySQL, MariaDB, Oracle e SQL Server.
    <br><br>
    <strong>Preços do Amazon RDS</strong>
    <br>
    Preços baseados na dimensão de instâncias EC2
    <br>
    Free tier: 750 horas de uso de instâncias db.t2.micro Single-AZ do Amazon RDS, 20 GB de armazenamento de banco de dados de SSD e 20 GB de armanezamento de backup.
    <br><br>
    <a href="https://aws.amazon.com/pt/rds/"><strong>Documentação da AWS sobre o Amazon RDS</strong></a>
</p>
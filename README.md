### Bancos de Dados Relacionais (SQL) na AWS com Amazon RDS

<p align="justify">
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Explorando o Amazon RDS, um serviço de provisionamente e gerenciamento de banco de dados relacional na AWS.
    <br><br>
    <strong>Serviços utilizados</strong>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Amazon RDS;<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;AWS Lambda; e<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MySQL Workbench.
    <br><br>
    <strong>O que é um banco de dados relacional?</strong>
    <br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Um banco de dados relacional é um mecanismo de armanezamento que permite a persistência de dados e opcionalmente implementar funcionalidades, armazenando os dados em tabelas, que possuem relacionamentos entre si.
    <br><br>
    <strong>Tabelas de um banco de dados relacional</strong>
    <br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;São organizadas em colunas, onde cada coluna armazena um tipo de dados;
    <br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Os dados são armazenados em linhas da tabela;
    <br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Possuem uma chave primária (PK) que identificam de forma única cada registro de uma linha;
    <br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Possuem chaves estrangeiras (FK) que estabelecem o relacionamento entre tabelas; e
    <br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Utilizam índices para pesquisa rápida de dados.
    <br><br>
    <strong>Relacionamento entre tabelas em um banco de dados relacional</strong>
    <br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1:1 duas tabelas se relacionam de forma direta onde a chave primária de uma tabela é utilizada uma única vez em outra.
    <br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1:n duas tabelas se relacionam de forma direta onde a chave primária de uma tabela é utilizada várias vezes em outra.
    <br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;n:n acontece de forma indireta entre duas tabelas, gerando de uma terceira tabela. Na prática ocorrem dois ou mais relacionamentos um para vários.
    <br><br>
    <strong>Sobre o Amazon RDS</strong>
    <br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;O Amazon Relational Database Service (Amazon RDS) facilita a configuração, a operação e a escalabilidade de bancos de dados relacionais na nuvem. Fornece capacidade econômica e redimensionável e automiza o provisionamento de hardware, configuração de bancos de dados, aplicação de patches e backups.
    <br><br>
    <strong>Mecanismos de banco de dados na Amazon RDS:</strong> Amazon Aurora, PostgreSQL, MySQL, MariaDB, Oracle e SQL Server.
    <br><br>
    <strong>Preços do Amazon RDS</strong>
    <br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Preços baseados na dimensão de instâncias EC2
    <br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Free tier: 750 horas de uso de instâncias db.t2.micro Single-AZ do Amazon RDS, 20 GB de armazenamento de banco de dados de SSD e 20 GB de armanezamento de backup.
    <br><br>
    <a href="https://aws.amazon.com/pt/rds/"><strong>Documentação da AWS sobre o Amazon RDS</strong></a>
    <br><br>
    <strong>Atividade prática</strong>
    <br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Criar uma instância RDS;<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Acessar com o MySQ Workbench e criar tabelas e inserir dados;<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Criar uma função Lambda para consultar dados em tabelas do RDS; e<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="https://github.com/cassianobrexbit/dio-live-rds">Código do instrutor</a>
    <br><br>
    <img src="https://github.com/lucasrmagalhaes/sql-aws/blob/main/assets/img/Arquitetura%20de%20Tabelas.jpg" alt="Arquitetura de Tabelas" title="Arquitetura de Tabelas" />
    <br><br>
    <img src="https://github.com/lucasrmagalhaes/sql-aws/blob/main/assets/img/Arquitetura%20do%20Sistema.jpg" alt="Arquitetura de Sistemas" title="Arquitetura de Sistemas" />
</p>
### Bancos de Dados Relacionais (SQL) na AWS com Amazon RDS

<p align="justify">
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Explorando o Amazon RDS, um serviço de provisionamente e gerenciamento de banco de dados relacional na AWS.
    <br><br>
    <strong>Serviços utilizados</strong>
    <br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Amazon RDS;
    <br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;AWS Lambda; e
    <br>
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
    <br><br>
    <strong>Criando queries</strong>
</p>

- Criar um database: 
```mysql
CREATE DATABASE PERMISSIONS_DB;
```

- Acessar o db criado:
```mysql
USE PERMISSIONS_DB;
```

- Criar uma tabela de usuários:
```mysql
CREATE TABLE user (
  id bigint(20) NOT NULL, 
  email varchar(40) NOT NULL,
  username varchar(15) NOT NULL,
  password varchar(100) NOT NULL,
  PRIMARY KEY (id)
);
```

- Criar uma tabela de carrinho de compras:
```mysql
CREATE TABLE role (
  id bigint(20) NOT NULL,
  name varchar(60) NOT NULL, 
  PRIMARY KEY (id)
);
```
- Criar uma tabela user roles:
```mysql
CREATE TABLE user_roles (
  user_id bigint(20) NOT NULL,
  role_id bigint(20) NOT NULL,
  FOREIGN KEY (user_id) REFERENCES user (id) ON DELETE RESTRICT ON UPDATE CASCADE,
  FOREIGN KEY (role_id) REFERENCES role (id) ON DELETE RESTRICT ON UPDATE CASCADE,
  PRIMARY KEY (user_id, role_id)
);
```

- Descrição da tabela:
```mysql
DESC user
```

- Inserindo dados em tabelas:
```mysql
INSERT INTO user VALUES (1, 'lucasdarosa.ti@gmail.com', 'Lucas', 'strongpasswd');
INSERT INTO user VALUES (2, 'igla@dio.me', 'Igla', 'strongpasswd');

INSERT INTO role VALUES (3, 'ADMIN');
INSERT INTO role VALUES (4, 'USER');

INSERT INTO user_roles VALUES (1, 3);
INSERT INTO user_roles VALUES (1, 4);
INSERT INTO user_roles VALUES (2, 4);
```

- Verificando:
```mysql
SELECT * FROM user_roles;
```

- Selecionando dados da tabela associativa:
```mysql
SELECT user.id, user.email, user.username, role.id AS role_id, role.name AS role_name
FROM user 
JOIN user_roles on (user.id=user_roles.user_id)
JOIN role on (role.id=user_roles.role_id);
```
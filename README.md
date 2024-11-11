# AtividadeBancoDadosSQL

## Passo a Passo: Criação de um banco de dados
Tutorial de como criar um banco de dados SQL que organiza as informações de 'Livros' , 'editora', 'autores' e 'assuntos'.
Este guia será dividido em etapas para demonstrar desde a criação de tabelas, chaves e até manipulação/consulta de dados.

## Resumo de uma estrutura SQL

* __CREATE__ - para criar 'banco de dados' pu 'tabelas'

* __ALTER__ - para adiconar ou modificar colunas

* __DROP__ - Para Remover 'banco de dados' ou 'tabelas'

* __INSERT__ - para adicionar/inserir os dados nas tabelas

* __UPDATE__ - para atualizar os registros

* __DELETE__ - para remover os registro

* __SELECT__ - para consultar e visualizar dados

* __CRUD__ - (Create, Read , Update , Delete)

## Passo 1: criação do Banco de Dados e das Tabelas
#### 1.1 Criando o DB (Banco de Dados)

```
CREATE DATABASE biblioteca;
USE biblioteca;
```

#### 1.2 Criando a tabela 'editora'
```
CREATE DATABASE editora (
    id_editora INT PRIMARY KEY AUTO_INCREMENT,
    nome_editora VARCHAR(100) NOT NULL,
    pais VARCHAR(50)
);
```

#### 1.3 Criando a teabela 'autor'

```
CREATE TABLE autor (
    id_autor INT PRIMARY KEY AUTO_INCREMENT,
    nome_autor VARCHAR(200)
    data_nascimento DATE
);
```

#### 1.4 Criando a tabela 'assunto'
```
CREATE TABLE assunto (
    id_assunto INT PRIMARY KEY AUTO INCREMENT,
    descricao_assunto VARCHAR(500) NOT NULL
);
```

#### 1.5 Criando a tabela 'livro'
```
CREATE TABLE livro(
    id_livro INT PRIMARY KEY AUTO_INCREMENT,
    titulo VARCHAR (150) NOT NULL,
    ano_publicacao YEAR,
    FOREING KEY(id_editora) REFERENCES editora (id_editora),
    FOREING KEY(id_autor) REFERENCES autor (id_autor),
    FOREING KEY(id_assunto) REFERENCES assunto (id_assunto)
);
```
<<<<<<< HEAD

#### 1.6 Criando uma tabela EXTRA
A tabela EXTRA vai servir para exemplificar a exclusão
```
CREATE TABLE extra(
    id INT PRIMARY KEY AUTO_INCREMENT,
    produtos VARCHAR(50),
    quantidade INT (20),
    preco DOUBLE NOT NULL
);
```

## Passo 2: editar tabelas usando 'ALTER'
Após a criação da tabela, podemos adicionar novos campos. Vamos adicionar uma coluna 'email' na ta tabela 'autor'

```SQL
ALTER TABLE autor
ADD COLUMN email VARCHAR(100);
```

=======
>>>>>>> 4a98eb9aa0994f9ee55d0775ab882003d595e584
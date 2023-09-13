# CRUD 

## Utilizando

- PHP 8.2
- MySql 8.0
- Bootstrap 5

Um Cadastro Simplificado de Usuário 

## Como instalar 


Criar a tabela no Banco de dados:

```sql
create table usuario(
    id INT NOT NULL primary key AUTO_INCREMENT,
    nome VARCHAR(255) not null,
    sobrenome VARCHAR(255) not null,
    idade INT(3) not null,
    sexo CHAR(1) not null
)
```

Configurar o arquivo Conexao.php dentro da pasta 'app/conexao': <br>

Adicione o codigo abaixo dentro da função getConexão(), caso seu banco seja Mysql ja está como padrão.<br>
Lembre-se de alterar os dados(dbname,user,password) na conexão de acordo com seu banco.

-Conexão para MySql
```php
 if (!isset(self::$instance)) {
           self::$instance = new PDO('mysql:host=localhost;dbname=SEU_BANCO', '', '', array(PDO::MYSQL_ATTR_INIT_COMMAND => "SET NAMES utf8"));
           self::$instance->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
           self::$instance->setAttribute(PDO::ATTR_ORACLE_NULLS, PDO::NULL_EMPTY_STRING);
       }

       return self::$instance;
```

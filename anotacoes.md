# Aula 01 - 21/03/2025

Conectando no MySQL por terminal:
```bash
mysql -h 127.0.0.1 -P 3306 -u root -p
mysql -h 127.0.0.1 -P 3306 -u ronan -p
mysql -h 127.0.0.1 -P 3306 -u Marina -p
```

Visualizar todos os bancos já criados

```sql
SHOW DATABASES;
```

## Usuários
Comando para gerenciamento de usuários:
```sql
---Criar um novo usuário
CREATE USER 'username'@'host' IDENTIFIED BY 'senha';
CREATE USER 'Marina'@'localhost' IDENTIFIED BY '123456';

CREATE USER 'ronan'@'localhost' IDENTIFIED BY '654321';

--Conceder todos os privilégios a um BD (Banco de Dados)
GRANT ALL PRIVILEGES ON database.* TO 'username'@'host';
GRANT ALL PRIVILEGES ON mysql.* TO 'ronan'@'localhost';
GRANT ALL PRIVILEGES ON mysql.* TO 'Marina'@'localhost';

--Conceder apenas alguns privigios
GRANT SELECT, INSERT, UPDATE ON database.table to 'username'@'host';

---Remover privilégios
REMOVE ALL PRIVILEGES ON database.*FROM 'username'@'host';

---Aplica as alterações de privilégios imediatamente
FLUSH PRIVILEGES;

---Alterar senha de usuário
ALTER USER 'username'@'host';

---Mostrar os privilégios do usuário
SHOW GRANTS FOR 'username'@'host';
SHOW GRANTS FOR 'Marina'@'localhost';

---Em caso de erro ao aplicar privilégios ou efetivar eles:
mysqlcheck --repair --databases mysql -u root

---Visualizar todos os usuários (Precisa ter privilégios SELEC ao Banco de Dados mysql)
SELECT User, Host FROM mysql.user;

```
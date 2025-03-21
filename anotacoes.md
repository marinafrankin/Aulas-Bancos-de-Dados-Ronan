# Aula 01 - 21/03/2025

Conectando no MySQL por terminal:
```bash
mysql -h 127.0.0.1 -P 3306 -u root -p
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

--Conceder todos os privilégios a um BD (Banco de Dados)
GRANT ALL PRIVILEGES ON database.*TO 'username'@'host';

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
```
```bash
sudo service postgresql status
```
Verifica se o serviço está ativo

```bash
sudo service postgresql start
```
Inicia o serviço

```bash
sudo service postgresql disable
```
Define o serviço para não carregar automaticamente

```bash
cd /etc/init.d
```
Local onde fica amarzenados os scripts de start, restart, status, stop

```bash
sudo /etc/init.d/redis-server status
```

```bash
sudo systemctl status redis-server
```
Comando que Controla os demons

```bash
sudo systemctl start postgresql
```
Outra opção do service

# Configurando o postgres

## Alterar a senha inicial

```bash
sudo passwd postgres
```
Digite a sua senha e redigite a mesma em seguida.

```bash
su postgres
```
logar com o usuário postgres.
A senha que será exigida é a mesma que acabamos de alterar.

```bash
psql -c "ALTER USER postgres WITH PASSWORD 'nova_senha'" -d template1
```
Onde nova_senha será a senha que você deseja.

```bash
sudo su postgres
```
Entra como superusuário

```bash
createuser --interactive
```
Criar um usuário superuser

```bash
createdb renanvt
```
Criar um banco de dados chamado renanvt

```bash
exit
```

```bash
su postgres
psql
```
psql loga direto do shell do postgres

```bash
\l
```
Lista todos os banco de dados

```bash
\q
```
Sai do psql
# Comando cron

- Utilizado para agendar tarefas recorrentes (que se repetem)
- Tarefas individuais são denominadas cronjobs e são gerenciadas pelo crontab (tabela do cron)

## cron - criar tarefa

```bash
crontab -e
```
Entrar no modo de edição das tabelas do cron

```bash
crontab -u <usuário> -e
```
Modificar tarefa de usuários

```bash
crontab -l
```
Ver sua tabela crontab

- As tabelas crontab de usuários ficam armazenadas no diretório /var/spool/cron/crontabs/
- A tabela global fica armazenada em /etc/crontab
- Para permitir que um usuário rode o comando cron sudo vi /etc/cron.allow

# crontab

- Possui seis colunas (campos) com as seguintes informações:
- <span style="font-color: red">Minuto  Hora  Dia  Mês  Dia_Semana  Comando</span>
- **Minuto:** Valores de 0 a 59 e o caracter curinga (*) que siginifica qualquer minuto
- **Hora:** Valores de 0 a 23 ou *
- **Dia:** Valores de 1 a 31 ou *
- **Mês:** 1 a 12, Jan a Dec, jan a dec ou * qualquer mês
- **Dia_Semana:** 0 a 7, Sun a Sat, sun a sat ou *
- **Comando:** O comando a ser executado ou script. Caminho do script ou do comando
- Podem-se especificar vários valores para um campo, bastantando para isso separá-los por **vírgulas.**
- Também é possível especificar um intervalor separando os valores iniciais e final por um **traço**

# crontab - exemplo

Crie a entrada no crontbat para executar o script:
```bash
crontab -e <enter>
```

Digite a entrada:
**00 19 * * * /home/renanvt/scriptteste.sh <enter>**

Salve o arquivo e fecha o editor de textos.

```bash
pgrep cron
```
mostrar o número do processo do cron

```bash
cat /var/log/syslog | grep cron
```
Ver um log das operações do cron

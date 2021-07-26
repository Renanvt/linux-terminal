# Comando at
Agendar um comando para que seja executado em um horário pré-determinado

##Sintaxe:

```bash
at <hora_de_execução>
```

- Após digitar o comando acima, o terminal irá aguardar pelas instruções a serem realizadas
- Depois de digitar todos os comandos, tecle CTRL+D para sair do at

- È Possível visualizar a fila de agendamento do at através dos comandos at -l ou atq
- Para saber quais comandos serão executados basta entrar no diretório /var/spool/cron/atjobs e ler o conteúdo dos arquivos de texto localizados
- Para excluir um job digite o comando atrm <nº_comando>

# Exemplos:

Copiar o arquivo de um diretório atual para outro diretório em tempo determinado

```bash
touch testeat
mkdir /teste
```

```bash
at 20:00 <enter>
```

```bash
sudo cp /home/renanvt/testeat /teste
```
Ctrl+D para sair

```bash
at -l
```
Mostra a fila de agendamento

Agendar os comandos que estão dentro de um arquivo
```bash
sudo vi agendamento.txt
```
**#Criar diretório**
mkdir /agendamento
**#Vai pro diretório**
cd /agendamento
**#Cria o arquivo**
touch teste-at-OK

```bash
at -f [arquivo] [horário_execução]
at -f agendamento.txt 20:08
```

# At - Privilégios de Acesso

**/etc/at.allow** - Contém os usuários que têm permissão de executar as tarefas.
**/etc/at.deny** - Contém os usuários que não possuem permissão de executar as tarefas com o at.

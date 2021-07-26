# FAZER BACKUP DOS ARQUIVOS

```bash
lsb_release -a
```
Visualizar a versão atual do debian e seu codinome

Editar o arquivo sources.list, porque esse arquivo está no momento configurado para apontar para a versão atual. Queremos apontar para a nova versão. Então primeiramente descobrimos o nome do codinome da nova distribuição ou versão

```bash
vi /etc/apt/sources.list
```

Para troca todos as intâncias que contém o codinome da versão atual, para o codinome que aponta para nova versão utilizamos o comando `sed`

```
sed -i 's/[nome_antigo]/[novo_nome]/g' [caminho_arquivo]
```

```
sed -i 's/[codinome_antigo]/[codinome_atual]/g' /etc/apt/sources.list
```
Substitui todas as intâncias do codinome antigo para o atual de uma vez só dentro do arquivo sources.list
<br/>
`g` = global. Faz o comando globalmente no arquivo<br/>
`s` = substitua
<br/><br/>
```bash
apt-get update
```
Atualiza a lista de pacotes

```bash
apt-get upgrade
```
Fazer o upgrade do sistema, atualiza os pacotes atuais. Isso ajuda a minimar o impacto na atualização da distribuição

```bash
apt-get -u dist-upgrade
```
Atualiza a distribuição do Linux

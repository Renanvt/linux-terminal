```bash
apt-get install mysql-server [num_versão]
```

## Ou

```bash
asdf plugin-add mysql
```

```bash
asdf list-all mysql
```

```bash
asdf install mysql [VERSION]
```

```
asdf global mysql [VERSION]
```

### reiniciar o servido mysql

```
/etc/init.d/mysql restart
```



# 1. Baixar o pacote do repositório apt do MySQL:


```bash
wget -c https://repo.mysql.com//mysql-apt-config_0.8.14-1_all.deb
```

Para saber qual a versão do repositório baixar, acessar a página https://dev.mysql.com/downloads/repo/apt/ (você pode baixar o pacote a partir desse endereço também via navegador).

# 2. Instalar o pacote do repositório usando dpkg:

```bash
sudo dpkg -i mysql-apt-config_0.8.14-1_all.deb
```

1. Pressione OK na tela de Configuração de pacotes que irá aparecer:
2. Escolha a opção Ok na tela seguinte, com as setas de direção do teclado, e com um tab selecione <Ok> novamente. Pressione Enter para prosseguir:
3. Aguarde enquanto o mysql-apt-config é configurado:

# 3. Instalar o MySQL Server

Primeiro, atualize as listas de pacotes dos repositórios do sistema:

```bash
sudo apt update
```

E então instale o pacote do MySQL Server com apt:

```bash
sudo apt install mysql-server
```

1. Uma tela para configuração de senha de root será aberta. Entre com uma senha segura e pressione <Ok>:
2. Repita a senha na tela seguinte para confirmar, e pressione novamente <Ok>:
3. A tela seguinte traz uma explicação sobre o novo método de autenticação do MySQL 8, baseado em métodos melhorados de hash SHA-256. Pressione <Ok> após ler a mensagem:
4. Na tela seguinte você irá selecionar o plugin de autenticação do MySQL Server. Use a opção recomendada – Use Strong Password Encryption – e pressione <Ok>.

Agora é só aguardar enquanto a instalação e configuração do MySQL Server 8 são realizadas.

# 4. Rodar script para configurar instalação segura com o comando a seguir:

```bash
sudo mysql_secure_installation
```

1. Entre com a senha de root (não aparece nada enquanto você digita). Logo após, pressione simplesmente Enter, pois não será necessário configurar o componente VALIDATE PASSWORD. Pressione Enter novamente na sequência, pois não queremos alterar a senha de root do MySQL agora:
2. Responda à pergunta “Remove anonymous users?” com y (yes), pois queremos remover usuários anônimos do sistema.
3. Também iremos desabilitar o login remoto do root e remover o banco de dados de testes interno.. Responda y às perguntas “Disallow root login remotely?” e “Remove test database and access to it?“.
4. Por fim, recarregue as tabelas de privilégios de acesso, respondendo y também à pergunta “Reload privilege tables now?“.

# 5. Verificar o status do serviço:

```bash
sudo systemctl status mysql
```

# 6. Iniciar serviço, se necessário:

```bash
sudo systemctl start mysql
```

# 7. Habilitar inicialização automática do MySQL Server

```bash
sudo systemctl enable mysql
```

# 8. Agora vamos instalar o IDE MySQL Workbench

```bash
sudo apt install mysql-workbench-community
```

# 9. Teste a instalação do MySQL Server acessando o servidor pelo terminal:

```bash
sudo mysql -u root -p
```

Forneça a senha de root do MySQL quando solicitado. Se a conexão for realizada com sucesso,a parecerá o prompt do mysql no terminal. Experimente executar um comando SQL para testar, como o SHOW DATABASES:

# Alterar arquivo de configuração

```bash
vi /etc/mysql/my.cnf
```
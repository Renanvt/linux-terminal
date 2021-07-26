```
whoami 
```
Quem eu sou no sistema
```
man 
```
Manual de comandos

```
mkdir 
```
Cria diretório

```
rm
```
remover diretório

```
chown 
```
change owner 

```
pwd
```
 onde estamos, print working directory

```
cd $HOME
```
 Voltar para a home

```
cd ~ 
```
Voltar para home

```
echo  ~
```
  mostra a variável home

```
cd 
```
volta pro home

```
df -h
```
  Listar dispositivos que estão montados e seus pontos de montagens

```
ps
```
  Lista processos dos aplicativos que estão em execução

```
less arquivo
```
 Mostra o arquivo sem edita-lo

```
echo
```
  Escreve qualquer coisa no STDOUT (Standard output)

```
touch a.txt
echo "hello world" > a.txt
```
O conteúdo anterior é substituído pela nova string

```
echo "hello world" >> a.txt
```
O conteúdo anterior é contatenado com a nova string

```
cat a.txt
```
 Concatena arquivos, lê tudo em memória antes de mostrar

```
more a.txt 
```
Mostra o arquivo como o cat

```
ps aux
```
Mostra todos os processos rodando no sistema

```
ps aux | more
```
Mostra todos os processos rodando no sistema com o as teclas de navegação do teclado

```
| 
```
Pipe - Liga o estandard output de um comando ao standart input de outro comando

```
ps aux | less
```
Faz a mesma coisa que o more, porém com streams, inves de carregar tudo na memória

```
ln -s a.txt b.txt
```
Cria um link simbólico

```
tail -f b.txt
```
vê o final do arquivo b.txt, se pendurando ao final do arquivo com -f. Ùtil para monitorar um arquivo de log em produção

```
ps aux | grep bash
```
Filtra a saída do ps para só mostrar as linhas que contem a palavra bash

```
Grep 
```
 Globally search a regular expression and print

```
sudo apt install silversearcher-ag
ps aux | ag bash | awk '{print $2}'
```
Filtra somente pela 2º coluna<br/>
awk - Linguagem interpretada
<br/>
**Ctrl + r**
Busca no histório de comandos 

```
rm b.txt 
```
Apaga o arquivo

```
mv b.txt foo
```
Move o arquivo b.txt para a pasta foo 

```
rm -Rf foo
```
Apagar um diretório

```
chmod 777 nome-do-arquivo
```
Da permissão de execução para o arquivo file.txt

```
echo $PATH
```
Vê o path

```
which echo
```
Vê o path do comando echo

```
echo $USER
set | less
```
Vê todas as variáveis de ambiente

```
sudo reboot
```
reinicia o sitema 
<br/>
# Shell:
- Bash -> Bourne Again Shell<br/>
- Tcshell<br/>
- zsh<br/>

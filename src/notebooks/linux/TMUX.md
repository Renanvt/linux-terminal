```
sudo apt-get update
sudo apt-get install tmux
```
Para instalar o tmux no  Ubuntu

```
man tmux
```
Manual do tmux

```
tmux -v
```
Verifica a versão

```
temux new
```
Abrir uma nova sessão

```
tmux new -s [session_name]
```
Cria uma nova sessão nomeada

```
tmux ls
```
lista as conexões ativas

```
tmux attach -t [connection]
```
Conectar a sessão com o nome específico


# Atalhos:

## CTRL + B - Informa ao tmux que um comando será executado (prefix)
## CTRL + B + C - Criar uma nova janela
## CTRL + B + nº da janela -> Vai para a janela de número especificado
## CTRL + B + top -> Vai para o topo
## CTRL + B + l -> vai pra última janela que eu estava
## CTRL + B + N -> Próxima janela
## CTRL + B + P -> Janela anterior
## CTRL + B + , -> Renomeia uma janela
## CTRL + B + w -> Lista todas as janelas
## CTRL + B + d -> Detached, sair do tmux

# Uso de painés
## CTRL + B + % - Dividi a janela verticalmente
## CTRL + B + Tecla de navegação - Muda de uma janela pra outra
## CTRL + B + PRESSIONADO + Tecla de navegação - Redimensiona a janela atual
## CTRL + B + o -> Alterna entre as janelas
## exit -> fecha o painel atual
## CTRL + B + " - Dividir a janela horizontalmente
## CTRL + B + x - Elimina o painel
## CTRL + B + q - Mostra o número do painel

# Sessões:
No temux é possível criar uma sessão compartilhada utilizando a mesma conexão com terminais diferentes

```
tmux
```
Cria uma nova sessão

```
tmux new -s [name]
```
Começa uma nova sessão com um nome

```
tmux attach #
```
Começar uma sessão anexada

```
tmux attach -t [name]
```
Se a sessão tmux tiver nome

```
tmux ls
```
Listar todas sessões temux

```
tmux kill-session -t 0
```
Fecha tudo que estava aberto na sessão 0

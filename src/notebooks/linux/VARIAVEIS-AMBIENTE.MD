As variáveis de ambiente permitem mudar o shell de várias formas para adaptá-lo às necessidades do usuário<br/>
## Exemplo de variáveis de ambiente:

**PS1**            Prompt da linha de comandos

**HOME**       Diretório /home de um usuário

**PATH**         Lista de diretórios vasculhados quando um comando é executado

# Verificar conteúdo de variáveis de ambiente

Comando env (todas as variáveis):
```
env
```

Comando echo (variável específica):
```
echo $NOME_VARIÁVEL
```

```
echo $PATH
```
A variável path contém um monte de caminhos de diretórios que contém arquivos executáveis, separados por :

# Criar variáveis de ambiente

Adicionar um caminho à variável PATH:
**PATH=$PATH:/novocaminho**

```
mkdir /testevar
```

```
PATH=$PATH:/minhavar
```
Anexa a variável de ambiente PATH um novo diretório chamado /minhavar

Criar uma variável de ambiente:
**MINHAVAR=meuconteúdo**
```
FRUTA=laranja
```

```
echo $[minha_var]
echo $FRUTA
```
Exibe o conteúdo da variável fruta

As variáveis assim criadas possuem escopo local - são válidas apenas no shell atual. Para tornar seu **escopo global**, exporte-as com o comando **export**:

**export MINHAVAR**
```
export FRUTA
```

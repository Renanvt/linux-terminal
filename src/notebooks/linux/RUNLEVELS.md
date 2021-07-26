- Ao se iniciar o Linux, são usados diversos scripts presentes no diretório /etc para configurar o sistema e mudar de um nível de execução a outro
- Esse processo varia um pouco entre as distribuições

# Processo init

init - Inicialização do controle de processos. È o pai de todos os processos, criados a partir de um script armazenado em /etc/inittab.


PID: 1

Um processo é um programa em execução

Todo processo linux possui um PID (Process Ident File) Identificador de processo

# Runlevels - Níveis de Execução

- O conceito de Níveis de Execução especifica as diferentes formas pelas quais um sistema pode ser utilizado e o controle sobre quais serviços rodarão.
- Os níveis de execução são especificados pelos números inteiros de 0 a 6
- O procsso init é responsável por levar o sistema ao nível de execução padrão

# Inicialização do Sistema - Runlevels

Runlevels:

**0** - Sistema Desligado<br/>
**1, S, s** - Modo Monousuário. Empregado pra fazer manutenção do sistema. Somente o essencial é executado.<br/>
**2** - Multiusuário; Padrão no Debian. com compartilhamento de arquivos NFS desabilitado.<br/>
**3** - Modo multiusuário com todos os serviços habilitados. Padrão no Red Hat, sem GUI.<br/>
**4** - Não usado<br/>
**5** - Multiusuário completo com login gráfico<br/>
**6** - Reinicialização do sistema.<br/>

# /etc/init.d

- Diretório que contém scripts de inicialização/encerramento para cada serviço do sistema.
- Exemplo: /etc/init.d/sshd
- Esses scripts aceitam argumentos como start, stop, restart, status e reload.
- Esses scripts não são executados diretamente pelo processo init. Em vez disso, os diretórios /etc/rc0.d a /etc/rc6.d possuem links simbólicos para esses scripts

## /etc/inittab FOI SUBSTITUÍDO PELOS ARQUIVOS DO DIRETÓRIO /etc/init/

# /etc/rc0.d a /etc/rc6.d

- Os links são nomeados nos formatos **KNNnome** e **SNNnome**
- **K** = Kill ("finalizar") Serviços que não deverão rodar naquele runlevel; executados primeiro
- **S** = Start ("iniciar") Serviços que deverão rodar no runlevel.
- **NN** = número de sequência (ordem de execução dos scripts)
- **Nome** = Identificação dos scripts


# Comandos init e telinit


O comando **telinit** muda o **runlevel** em tempo de execução.

Na verdade, o telinit é um link para o init

Um nível de execução é uma configuração de software do sistema que permite que apenas um grupo selecionado de processos existam em um dado momento
```
telinit [nº_runlevel]
```

```
telinit 0
```
  Desligar o sistema.

```
runlevel <enter> 
```
 Mostra o runlevel préviio e o atual.q

O telinit pode dizer ao init quanto tempo ele deve esperar entre o envio de um sinal SIGTERM aos processos e o envio de um sinal SIGKILL. O padrão é 5 segundos, mas isso pode ser alterado com a opção -t, por exemplo para 10 segundos ao reiniciar o sistema (runlevel 6):

```
 telinit -t 10 6
```

## Sintaxe do comando init:

```
init[valor]
```
Muda runlevel para valor
- Onde [valor] é o número do nível de execução desejado ou uma outra opção, como:
- **Q ou q**  - Diz ao init para re-examinar o arquivo /etc/inittab
- **S ou s** - Alternar para o modo de usuário único (single mode)
- **U ou u** - Diz ao init para reexecutar a si mesmo, preservando o runlevel atual.
- **a,b,c** - Diz ao init para processar apenas as entradas de arquivos no arquivo /etc/inittab que tenham os runlevels a,b ou c.
```
telinit q
```
Aplica as mudanças realizadas em /etc/inittab

## Exemplos:

Desligar o sistema:
```
init 0
```

Reiniciar o sistema:

```
init 6
```

Reler o /etc/inittab:
```
init q
```

Recarregar a si próprio:
```
 init u
```

Entrar em modo de usuário único:
```
init 1
```

ou

```
init S
```

O comando telinit, por se tratar de um atalho para o init, funciona da mesma maneira

## CUIDADO!!!: Nunca configure os runlevels 0 ou 6 no arquivo /etc/inittab, pois seu sistema não conseguirá mais inicializar corretamente!


# Gerenciando os links de runlevel no Debian


Podemos gerenciar os links de scripts de nível de execução usando o utilitário **sysv-rc-conf**, que pode ser instalado com o comando a seguir:



```
apt-get install sysv-rc-conf
```

E aberto com o comando:

```
sysv-rc-conf
```

Com esse utilitário podemos consultar e também ativar ou desativar scripts em cada nível de execução no console com facilidade. Veja a tela do utilitário em execução:

Basta navegar pelos itens com as setas de direção do teclado, e com um toque na barra de espaços você pode ativar ou desativar os scripts de acordo com o runlevel que é mostrado no cabeçalho das colunas.

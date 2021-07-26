**background** - segundo plano<br/>
**foreground** - vinculado ao terminal<br/>

**Tarefa**: um processo colocado em background<br/>
Possui número de identificação, sempre a partir de 1
**num tarefa <> num de id**<br/>
o número da tarefa é utilizado pra fazer controle das tarefas

**bg** - È colococado um processo em background para poder liberar o terminal de onde ele foi iniciado. Desvincula ao terminal. È necessário digitar ctrl + z para pausar o processo antes

**fg** - Coloca a tarefa especificada em foreground. Revincula ao terminal.


# Exemplo:

## Colocando o terminal como processo pai do gimp

```
gimp
```
Abre o programa gimp no terminal, impossibilitando o uso do terminal. Experimente ctrl + z que o processo fica parado(pausado) (equivale a enviar o sinal 20 - TSTP)

**obs.: Se fechar o processo pai, todos os processos filhos serão terminados imediatamente**

```
bg
```
Coloca a tarefa atual (+) em segundo plano

```
bg [nome_ou_num_tarefa]
```
Coloca a tarefa especificada em segundo plano

```
gimp &
```
Abre o programa gimp no terminal, colocando ele em segundo plano

```
fg
```
Coloca a tarefa devolta em primeiro plano

```
fg [nome_ou_num_tarefa]
```
Coloca a tarefa especificada devolta em primeiro plano

`[1]` **3642**<br/>
`num da tarefa`    **num do processo**

## Descobrir os números das tarefas - Comando jobs

```
jobs [opção]
```
Lista as tarefas ativas
<br/>
**-l** Listar também os PIDs



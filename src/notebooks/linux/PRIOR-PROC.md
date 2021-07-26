A prioridade indica quanto tempo relativo de cpu o kernel do sistema aloca a um processo, quanto mais tempo o processo tiver pra rodar, mais prioridade ele tem.
Quanto maior a prioridade maior porcentagem que a cpu usa, ou seja o processo ganha maior "fatia" de tempo de execução pelo processador.

Prioridade de numero elevado signifca que o processo tem prioridade baixa no sistema
Prioridade de numeros menores significa que o processo tem prioridade mais alta

### PRI
```
top / ps -l
```

# Alterar as propriedades de execução dos processos

## nice / renice
Incrementa ou decrementa uma proridade

**nice** - quanto menor, maior a prioridade do processo. Por padrão os nice de usuário são ajustado com 0.<br/>
**-20** prioridade máxima de um processo <br/>
**+19** menor prioridade possível <br/>

**números negativos indicam prioridades maiores**

# comando nice

sintaxe:
```
nice -n [ajuste] [comando]
```

**-n** indica que o valor que vem a frente é um num nice </br>
**ajuste** - num nice. 1 a 19 para usuários normais. -20 a 19 para rot. Padrão é 10 <br/>
**comando** - comando a ser utilizado com o comando nice para alterar a prioridade dele <br/>

```
nice -n 12 inkscape
```
diminui a prioridade em 12 do inkscape

```
sudo nice -n -16 inkscape
```
Aumenta a prioridade em -16 do inkscape

# Mudar a prioridade em tempo de execução - comando renice

Sintaxe:

```
renice +|- [novo_num_nice] [opções] alvos
```

**-u** - Interpreta os alvos como nome de usuários inves de PIDS
**-p** Interperta os alvos como PIDs (padrão)

Exemplos
```
renice 15 15132
```
Incrementa a coluna de prioridade em 15 unidades

```
sudo renice 3 -u renanvt
```
Incrementa a coluna de prioridade para o usuário

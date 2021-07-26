Processos monitoriam sinais que são enviados pelo kernel ou pelo usuários.

sinais são números inteiros e dizem para um processo oque ele deve fazer

è possível controlar os processos utilizando sinais

# Alguns sinais comuns:

**HUP**    `1`    Desconectar - utilizado para demons  reler arquivos de confi sem interroper um processo em si

**INT**     `2`    Interromper. CTRL + C

**TERM**   `15`   Terminar de forma "elegante". Processo finaliza sem causar problemas

**KILL**    `9`    Termina imediatamente o processo. Interrupção de emergência. Mata o processo

**TSTP**    `20`    Parar/Pausar a execução;    Ctrl+Z

**CONT**   `18`    Continuar a execução de um processo que foi pausado com um processo de num 20

# Enviar sinais a um processo: comando kill

```
ps -l
ps aux
```
Descobre o número do processo

Sintaxe:
```
kill - sinal PID
```
Encerra o processo
```
kill -SIGINT PID
```
Encerra um processo com o sinal int

```
kill -l numero_sinal 
```
Retorna o nome do sinal

# Comando killall

Termina processos que são associados com programas cujos nomes são fornecidos. Simplesmente descarrega o programa da memória

```
killall [opção] nome_programa
```

**-i** modo interativo

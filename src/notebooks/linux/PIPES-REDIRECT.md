### stdin
### stdout
### stderr

Um comando gera uma saída, que é incorporada por outro comando que gera outra saída, que pode ser incorporada por outro comando e assim por diante até que o resultado dos comandos apareça em um local específico (tela ou dentro de arquivo)

# Arquivos de Dispositivos:
No Linux ou Unix tudo são arquivos

Tudo pode ser mapeado para o sistema de arquivos

Os programas podem interagir com os dispositivos de hardware de uma forma padronizada. 

Os dispositivos podem ser acessados por meio de mapeamentos denominados Arquivos de Dispositivos
Ex.: /dev/sda

Um Arquivo de Dispositivo é um objeto do sistema que ofereçe uma interface para o dispositivo em si.

O Kernel associa os drivers de dispositivos aos arquivos de dispositivos

# Descritores de Arquivos:
Abstração de uma identificação para acessar um arquivo.

Existem três descritores de arquivos:

- Entrada Padrão (stdin)

- Saída Padrão (stdout)

- Erro Padrão (stderr)

**Entrada Padrão** - stream (fluxo) para entrada de texto. Vinculada ao teclado.

`Descritor de Arquivos 0`

**Saída Padrão** - stream para saída normal dos programas. Vinculada ao terminal ou janela de terminal (interface gráfica)

`Descritor de Arquivos 1`

**Erro Padrão** - stream de saída de texto, usado para exibir mensagens de erro.

`Vinculado ao terminal.`
`Descritor de Arquivos 2`

# Pipes
**|** - Permite juntar dois ou mais comandos de modo que são executados em sequência

ex:
```
ls -l | less
```
less <- stdout ls -l

O pipe canaliza a saída de um programa para entrada de outro

Se forem usados mais de dois comandos com redirecionamentos, damos o nome de **pipeline** à operação resultante.

Ex:

```
ls /etc | sort -r | less
```

Lista o conteúdo do diretório /etc, redireciona a saída para o comando sort, invertendo a ordem e o resultado da operação é redirecionado para o comando less que vai paginar

# Redirecionamentos
Operador de redirecionamento > <br/>
Redireciona a saída para um novo arquivo

Ex.:
```
ls -i > inodes.txt
```
Exibi a listagem de inodes e salva dentro de um arquivo chamado inodes.txt

As saídas redirecionadas para um arquivo não são exibidas na saída padrão (terminal), excento os erros padrão.

O operador de redirecionamento **">"** cria arquivos, se o arquivo já existe ele é substituito

Para não sobrescrever o conteúdo de um arquivo já existente, use o operador **>>**

O operador **>>** anexa uma frase ao final do arquivo e não substitui o conteúdo do arquivo


# Comando echo
O comando echo, ecoa o texto que será colocado entre aspas. Exemplo:

```
echo "Lista de arquivos do diretório"
```
Exibe: Lista de arquivos do diretório

```
echo "Lista de arquivos do diretório" >> texto.txt
```

## Redirecionamento de entrada
**<** = Redirecionamento da entrada lê a partir de um arquivo
```
cat < /etc/group > /tmp/grupos
```

O conteúdo de /etc/group vai ser lido pelo comando cat e depois será enviado para um novo arquivo /tmp/grupos


```
ls -zz
```
Comando não existe, erro

```
ls -zz > erro.txt
```

```
cat erro.txt
```
Não tem nada dentro, pois o erro padrão não é a saída padrão

Como colocar o erro padrão para um arquivo

```
ls -zz [num_descritor_de_arquivos]> arquivo
ls -zz 2 > erro.txt
```
Pega o erro padrão e redireciona pra dentro do arquivo erro.txt

# Comando tee
Permite enviar a saída de um comando para um arquivo e para a tela ao mesmo tempo

## Sintaxe:
```
tee [opções] arquivos
```
**-a**    Anexa aos arquivos, em vez de sobrescrevê-los

### Exempo 1:
```
ls -l | tee arquivo1
```
A saída do comando ls -l vai pro comando tee por meio de um pipe, o comando tee grava dentro do arquivo a saída de ls -l e tambem redireciona pra tela

### Exemplo 2:
```
ls -i | tee arquivo1 | less
```
Idem ao exemplo 1, porém redireciona a saída de outro pipe para o comando less. Dentro do arquivo 1 o conteúdo não será paginado, pois foi feito antes do comando less

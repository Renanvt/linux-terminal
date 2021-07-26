~ - Diretório padrão do usuário
# O usuário logado atualmente é root

O shell original foi escrito por Stephen Bourne em 1977, e o nome dele era SSH, desenvolvido especificamente pro projeto GNU

BASH = Bourne-Again Shell

```
comando [opções] [argumento] <enter>
```
Sintaxe padrão de um comando


**cd ~** = Vai pro diretório padrão do usuário

**cd -** = Volta pro diretório anterior

**cd ..** = Volta pro pai do diretório atual

```
cd /home; ls -l
```
vai pro diretório home e exibi o diretório


# Visualizando o diretório corrente com o comando pwd no Linux


# Comando PWD 

O comando **pwd** permite imprimir o nome do diretório de trabalho atual (caminho completo) no terminal do Linux / Unix. Desta forma, podemos saber qual o diretório aberto no momento.


## Sintaxe


```
pwd [opções]...
```

- **-L, –logical** - usar o PWD do ambiente, mesmo que ele contenha links simbólicos
- **-P, –physical** - Evitar todos os links simbólicos
- **–help** - Mostrar a ajuda e sair
- **–version** -  Mostrar informações sobre a versão e sair
-  Se nenhuma opção for especificada, será assumida por padrão a opção **-P** (evitar todos os links simbólicos).

# Comando touch
- Permite alterar o registro de data e hora de modificação e acesso de um arquivo; Cria um arquivo de texto vazio.
- Sintaxe:

```
touch [opções] nome_arquivo <enter>
```

- **-a** - Altera a hora de acesso
- **-m** - Altera a hora de modificação
- **-t** YYMMDDhhmmss - Configura a hora digitada

ex.:

```
touch -m -t 201012211400 arquivo
```

# Comando cut
- "Cortar" campos ou colunas selecionadas de cada linha de um arquivo; Imprime colunas ou campos demilitados por espaços ou outros caracteres especificados pelo usuário.

```
cut [opções] arquivo
```

- Opções:
- **-c**          Colunas, Posição de caractere
- **-f[n]**     Campos
- **-d[d]**    Delimitador

Exemplo:

```
cut -c1-6 arq1
```
Imprime as colunas de 1 a 6

```
cut -c4,8 arq1
```
Imprime as colunas 4 e 8

```
cut -d: -f3 arq1
```
Impre o campo 3 usando o caractere : como delimitador. Para usar o espaço como delimitador, use ' ' (espaço entre aspas simples). Mais exemplos:

```
cut -d: -f1 /etc/passwd 
```
(lista os usuários do sistema)

```
cut -d -f1,6 /etc/passwd 
```
(usuários e seus diretórios padrão)

```
cut -d' ' -f3 /etc/passwd
```

# Comando head

Mostra as primeiras linhas de um ou mais arquivos.

```
head [opções] arquivo
```

```
heard arq2
```
Mostra as **10** primeiras linhas de arq2

```
head -c50
```
Exibe os primeiros 50 bytes de um arquivo (ou k ou m para kilobytes e megabytes)

```
head -n15 arq2
```
Mostra as 15 primeiras linhas de arq2

```
head -n8 /etc/group
```
Mostra as 8 primeiras linhas do arquivo /etc/group

# Combinando head com cut

```
cut -d' ' -f2 arquivotouch | head -n5
```
Mostra somente os nomes das 5 primeiras frutas do arquivo arq1

# Comando sort

Organiza os dados de acordo com a necessidade dos usuários (de acordo com a primeira coluna e caracteres).

```
sort [opções] arq1
```

```
sort [opções] arq1 > arq_sorted
```

- Opções:
- **-f** Ignora o caso (maiuscula e minúsculas)
- **-n** Classificação Numerica
- **-r** Ordem reversa

# > = Redirecionar a saída pra um outro arquivo (cria um arquivo)

Por padrão a classificação é numérica ou alfabética pela primeira coluna do arquivo

Exemplo: Digite o arquivo a seguir e salve-o como arq4:

3 cde<br/>
2 bcd<br/>
1 abc<br/>

Digite o comando a seguir e verifica o resultado em arq5:
```
cut -c3-5 arq4 | sort > arq5
```

Cria um arquivo chamado numeros contento apenas os números do arq4 em ordem numérica:

```
cut -d' ' -f1 arq4 | sort > numeros
```

# Comando split

Divide um arquivo em várias partes em uma sucessão de arquivos com final aa, ab, ac, etc..

```
split [opções] arq_entrada arq_saídaX
```

- Opções:
- **--lines=n, -l=n**       n linhas p/ arquivo
- **-- bytes=n, -b= n **    n bytes por arquivo

Exemplo:

```
split -b 120 arq.conf arq-
```

Divide o arquivo arq.conf em várias partes com 120 bytes cada, com os nomes arq-aa, arq-ab, arq-ac, e assim sucessivamente.
Para unir novamente as partes do arquivo, use o comando cat:

```
cat arq-aa arq-ab arq-ab > arq.conf
```

## Comando split na prática

cp /etc/passwd /home/fabio<br/>
cd /home/fabio<br/>
ls<br/>
split -b 200 passwd pass-<br/>
ls -l<br/>
-----------------------------------------<br/>
cat pass-* > passwd-2<br/>
ls<br/>
cat passwd-2<br/>

# Comando Tail

Usado para ver as últimas linhas de um arquivo.

```
tail arq1
```
Mostra as 10 últimas linhas de arq1

```
tail -n 20 arq1
```
Mostra as 20 últimas linhas de arq1

```
tail -f /var/log/messages
```
Mostra as 10 últimas linhas dinamicamente, enquanto são geradas. Ùtil pra monitorar arquivos de log em tempo real

# Comando tac

Inverso do comando cat: envia os arquivos de texto para a saída padrão, com as linhas em ordem reversa.

```
tac [arquivos]
```

# Comando wc

World count. Exibe contagem de caracteres, palavras e linhas em arquivos

```
wc [opções] [arquivos]
```

- **-c** Contagem de caracteres
- **-l** Contagem de linhas
- **-w** Contagem de palavras

## Exemplo

Quantos grupos existem no meu sistema
```
wc -l /etc/group
```

# Comando uniq

Escreve em stdout uma entrada, eliminando linhas duplicadas adjacentes.
Para eliminar linhas duplicadas não-adjacentes, primeiro organize o arquivo com sort

```
uniq [opções] [entrada[saída]]
```
- **-d** Processa apenas as linhas que se repetem
- **-u** Processa apenas as linhas que não se repetem

```
uniq arquivo
```
Elimita todas as repetições do arquivo
```
uniq -d arquivo
```
Traz somente as linhas que se repentem, não mostrando as repetições das linhas
```
uniq -u arquivo
```

# Comando cp

Copia um arquivo ou diretório para outro local

```
cp [opções] origem destino
```

## Exemplos:
```
cp /home/adriano/arq1 /home/fabio/
```

Opções

- **-i** Pede confirmação interativamente, caso o local de destino esteja um arquivo com o mesmo nome
- **-r** Copia diretórios recursivamente, Copia o diretório e toda a árvore de diretórios dentro dele
- **-p** Preserva todas as informações. Se não usar essa opção o arquivo depois de copiado, terá data e hora atuais do momento que ele foi copiado e as permissões, proprietário e grupo padrões

## Mais exemplos do comando cp

```
cp /home/convidado/arq1 .
```
Copia o arquivo arq1 do diretório /home/renanvt para o diretório atual.<br/>
**.** = diretório corrent

```
cp /root/a* /home/
```
Copia todos os arquivos que se iniciam com a letra a do diretório /root para o diretório /home

```
cp arq[246]
```
Utilização de uma expressão regular. Copia todos os arquivos que começam com o nome arq que termina com 2 4 ou 6

# Comando rm

Utilizado para excluir arquivos e diretórios

Para excluir arquivos:
```
rm [opções] [arquivo_diretório]
```
Para excluir um diretório ocupado:
```
rm -r nome_diretório
```

```
rm [arquivo*]
```
Remove todos os arquivos que começa com o nome x e termina com qualquer letra

Opções:
- **-r** Exclui diretórios

# Comando rmdir
Remove um diretório (tem de estar vazio)

```
sudo rmdir [nome_diretório]
```

Remover um diretório que não esteja vazio

```
sudo rm -r [nome_diretório]
```

Comando rm -Rf /

Este comando remove recursivamente todos os arquivos e diretórios de seu sistema Linux. até a raiz.
NUNCA o execute!. Apaga tudo oque tem no computador!

# Comando mv
```
mv [opções] origem destino
```
Move o arquivo ou o diretório para o destino especificado

Opções
- **-i** COnsulta o usuário antes de mover arquivos

Exemplo:

```
mv /root/arq1 /home/
```
move o arquivo arq1 de /root para /home

```
mv /home/fabio/arq1 /home/fabio/arq2
```
Renomeia o arquivo arq1 para arq2.
Para isso, deve-se mover o arquivo de um diretório para o próprio diretório onde ele se encontra, trocando o nome do arquivo no final do comando

# Comando mkdir

Cria um ou mais diretórios.

```
mkdir [opções] nome_diretórios
```

Opções:
- **-m** Modo. Define direitos de acesso no modo octal
- **-p** Cria subdiretórios recursivamente

```
sudo mkdir -m 444 [nome_diretórios]
```
cria diretório com nível de permissão

```
sudo mkdir-p animais/peixes/tubarões
```
Cria diretórios recursivamente

```
sudo mkdir merluza pescada atum
```
Cria 3 diretórios ou pastas

```
sudo mkdir "peixe de aquário"
```
Cria a pasta, interpretando o conjunto de string como uma pasta só

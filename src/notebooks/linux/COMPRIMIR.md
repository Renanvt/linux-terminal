# comando gzip

Podemos comprimir arquivos usando a ferramenta gzip (GNU zip).

## Sintaxe:

```
gzip [parâmetros] [nome_do_arquivo]
```

Parâmetros:
- **-c**    -Extrai um arquivo para a saída padrão
- **-d**    -Descompacta um arquivo comprimido
- **-l**     -Lista o conteúdo de um arquivo compactado
- **-v**   -Exibe detalhes sobre o procedimento;
- **-r**    -Compacta o conteúdo de pastas;
- **-t**    -Testa a integridade de um arquivo compactado

```
gzip [nome_arquido]
```
Compacta o arquivo

```
gunzip
```
Extrair arquivos compactados com gzip
Equivale na verdade a gzip -d

## Exemplos

```
gzip testegzip.txt
```
O comando acima compacta o arquivo testegzip.txt. Os arquivos compactados com gzip recebem a extensão .gz.

```
gzip -d testegzip.txt.gz
```
O comando acima descompacta o arquivo testegzip.txt.gz; é o mesmo que:
gunzip testegzip.gz

# Comando bzip2
Também podemos compactar e descompactar arquivos com o bzip2
O bzip2 compacta melhor que o gzip diminuindo o tamanho ainda mais

## Sintaxe:
```
bzip2 [opções] [nome_do_arquivo]
```

Parâmetros:
- **-c**    -Extrai um arquivo para a saída padrão;
- **-d**    -Descomprime um arquivo comprimido;
- **-t**    -Testa a integridade de um arquivo compactado;

## Exemplos bzip2

```
bzip2 testegzip.txt
```
O comando acima compacta o arquivo testegzip.txt. Os arquivos compactados com bzip2 recebem a extensão .bz2

```
bzip2 -d testegzip.txt.bz2
```
O comando acima descompacta o arquivo testegzip.txt.bz2

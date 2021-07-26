# Comando locate

Permite encontrar arquivos por seus nomes.
Busca em um índice de arquivos, atualizado diariamente, o que torna essa busca mais rápida.

## Sintaxe:

```
locate <nome_arquivo>
```

Opções:<br/>
**-i**    Permite ignorar o caso<br/>
**-c**    Imprime o número de arquivos encontrados<br/>

O comando `updatedb` atualiza o banco de dados de arquivos imediatamente

# Comando which
O comando which informa a localização de um comando e exibe o caminho até seu executável

Sintaxe:
```
which <programa>
```

ex.:
```
which pwd
```
# Comando whereis
Este comando retorna o caminho de um programa executável, suas fontes e páginas de manual

Sintaxe:
```
whereis <programa>
```

Ex.:
```
whereis ls
```

Opções:<br/>
**-b**    Somente arquivos binários<br/>
**-m**    Somente páginas de manual<br/>
**-s**    Arquivos de código-fonte<br/>

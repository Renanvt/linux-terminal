Comando copy in, copy out

# Comando cpio
Realiza três operações(modos):
- Criar arquivamentos (archives);
- Extrair arquivamentos;
- Copiar arquivos de um local para outro.

Não é feita compactação nesses arquivamentos
Arquivamento é como se fosse um zip sem a compactação, arquivos que contém diversos outros arquivos

## Sintaxe:

```
cpio -o [opções] arquivos > arquivamento
```

```
cpio -i < arquivamento
```

```
cpio -p dir-destino < arquivos
```

- **-o**    Modo de saída de cópia (criar)
- **-i**     Modo de entrada de cópia (extrair)
- **-p**    Modo de passagem de cópia (copiar)

## Exemplos:

**cpio - Criar arquivamento**
Criar um arquivamento cpio com o conteúdo retornado do diretório atual:

```
ls | cpio -ov > arquivamento.cpio
```

**cpio - Extrair arquivos de um cpio**

```
cpio -idv < arquivo.cpio
```

**Copiar árvore de diretórios do diretório atual para o diretório /teste:**

```
find . -depth | cpio -pmdv ../teste
```

`find` - Comando de busca. Encontra todos os arquivos<br/>
**-depth** - Pega recursivamente todo o conteúdo do diretório atual incluindo seus subdiretórios<br/>
**d**    criar diretórios quando for necessário<br/>
**m**    reter hora de modificação dos arquivos<br/>
v    modo verboso<br/>

## Listar o conteúdo de um arquivo cpio
```
cpio -t <arquivamento.cpio
```

## Criar arquivo cpio com formato tar:
```
ls | cpio -o -H tar > arquivamento.tar
```

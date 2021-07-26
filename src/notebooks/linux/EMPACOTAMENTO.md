# Comando tar
Utilizado para empacotar arquivos
O comando tar não comprimir os arquivos.

## Sintaxe:
```
tar [parâmetros] [nome_do_arquivo.tar] [arquivo_de_origem]
```

Opções:
- **-c**    - Cria um novo arquivo tar;
- **-t**    - Exibe o conteúdo de um arquivo tar;
- **-p**    - Mantém as permissões originais do(s) arquivo(s);
- **-r**    - Adiciona arquivos a um arquivo tar existente;
- **-f**    - Permite especificar o arquivo tar a ser utilizado;
- **-v**    -Exibe detalhes da operação;
- **-x**    -Extrai arquivos de um arquivo tar existente (Desempacotamento);
- **-z**    -Comprime o arquivo tar resultando com o gzip;
- **-C**    -Especifica o diretório dos arquivos a serem armazenados

O arquivo de origem pode ser vários arquivos especificados em sequencia ou uma pasta

## Exemplos:
```
tar -cf plantas.tar bromedia.txt orquidea.txt
```
Cria o arquivo **plantas.tar**, contendo os arquivos **bromelia.txt** e  **orquidea.txt**

```
tar -rf plantas.tar araceas.txt
```
Adiciona o arquivo **araceas.txt** ao arquivo empacotado **plantar.tar**

```
tar -f plantas.tar --delete araceas.txt
```
Exclui o arquivo **araceas.txt** do **plantas.tar**

```
tar -cvf frutas.tar pasta_frutas
```
Empacota o diretório **pasta_frutas** no arquivo **frutas.tar**

```
tar -xvf plantas.tar
```
Extrai o arquivo plantas.tar no diretório atual

```
tar -xvf plantas.tar bromelia.txt
```
Extrair somente um arquivo de plantas.tar

# Tar + gzip ou bzip2

- O comando tar apenas empacota arquivos, mas não os comprime
- Para isso, devemos usar o tar juntamente com o gzip ou bzip2
- Para usar tar com gzip basta acrescentar ao tar o parâmetro -z. O arquivo resultante terá a extensão .tar.gz
- Para usar tar com bzip2 basta acrescentar ao tar o parâmetro -j. O arquivo resultante terá a extensão .tar.bz2

```
tar -cvzf plantas.tar.gz orquidea.txt aracea.txt
```
criar um tar compactado gzip

```
tar -xzvf plantas.tar.gz
```
extrair um tar compactado com gzip

```
tar -cvjf plantas.tar.bz2 orquidea.txt aracea.txt
```
criar um tar compactado com bzip2

```
tar -xvjf plantas.tar.bz2
```
extrair um tar compactadom com bzip2

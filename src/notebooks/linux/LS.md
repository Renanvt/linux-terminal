# Comando LS

Comando usado para listar arquivos em sistemas Unix ( e Linux, OS X, BSD, etc.)

Sintaxe:

```bash
ls [opções] [arquivo]
```

Usando **atalhos** do teclado. Pressione as teclas. **Ctrl + Alt + T** . Isso vai abrir o "Terminal".

# Algumas opções do ls

![Comandols](../../img/comando-ls.png)
![Comandols](../../img/comando-ls2.png)

# Status de saída do comando ls:
![Comandols](../../img/status-saida.png)


**PWD** = Descobrir que diretório estou atualmente
<br/>
**cd /** = mudar para o diretório Raiz
<br/>
**clear** = limpar a tela
<br/>
*.* e *..* são arquivos ocultos que fazem referência ao diretório atual e ao diretório pai
<br/>
**d** = Diretório
<br/>
**l** = link
<br/>
**-**  = Arquivo comum ( arquivo de usuário)
<br/>
**UID** - Identificação do usuário
<br/>
**GID** - Identificação do grupo
<br/>
**0** - Usuário Root  ou Grupo Root


## Combinar as opções entre si

```
ls -la
```
 = Mostra todos os arquivos no formado longo e também exibir os ocultos
```
ls - lh
```
 = Mostra o tamanho em formato legível por humanos (GB, KB, MB) e em formato longo
```
ls .
```
  = Mostra o conteúdo do diretório atual
```
ls ~ 
```
= Mostra o conteúdo do diretório padrão do usuário atual
```
ls  /Downloads
```
 = Mostra o conteudo de Downloads que está dentro do diretório atual
```
ls -lh /etc 
```
= Mostra o tamanho em formato legível por humanos (GB, KB, MB) e em formato longo da pasta etc
```
ls -lh /etc |  less 
```
 = redireciona a saída do ls -lh para o comando less. Comando less divide as páginas de modo que consiga ver todo o conteúdo. Letra Q - Sai do comando less
```
man ls 
```
= Página de manual do ls

## Combinações avançadas

Listagem longa, porém mostrando primeiro somente os diretórios, e depois os demais arquivos, e ainda por cima ordenando os itens em ordem alfabética reversa:

```
ls -lr --group-directories-first
```

 Listar os diretórios e subdiretórios de forma recursiva, mostrando também números de inode:


```
ls -iR
```

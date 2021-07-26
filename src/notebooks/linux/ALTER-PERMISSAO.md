Comando chmod - alterar as permissões de acesso a arquivo e diretórios no linux

Modo de permissões octal

Sintaxe:

```bash
chmod [permissões] [arquivo ou diretório]
```

Permissões:
Execução = 1

Escrita = 2

Leitura = 4


rwx

111

bit 1 - com permissão

bit 0 - sem permissão


--x Permisão somente de **execução**

001 = bin-> dec = `1`

-w- Permissão somente de escrita

010 = bin-> dec = `2`

r-- Permissão somente de leitura

100 = bin-> dec = `4`

Ao total temos 8 valores possíveis de valores de permissões


rw- Permissão de **leitura e escrita**

110 = bin -> dec = 4 + 2 = `6`

rwx - Dar **todas as permissões** de uma vez

111 = bin -> dec = 4 + 2 + 1 = `7`


rwxrw-rw-

rwx    rw-    rw-

111    110    110

7          6        6

**766** - Proprietário do arquivo tem permissão total, o grupo só de leitura e escrita, e outros de leitura e escrita



rw-r-----

rw-    r--    ---

110   100  000

6        4        0

**640** - O proprietário lê e escreve, o grupo só lê, e outros não tem permissão de acesso

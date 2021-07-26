```
ls -l
```

**Permissões    Links    Proprietário    Grupo    Tamanho    Data e Hora    Nome do arquivo**<br/>
drwxr-xr-x          2             renanvt         renanvt   4096             jan 22 23:03        Música

- **d** = Indica o tipo do arquivo ou diretório. (diretório)
- **-** =  arquivo comum de usuário
- **c** = arquivo de caractere
- **b** = arquivo de bloco
- **l** = link

as permissões são aplicadas em 3 conjuntos:<br/>
**Proprietário    Grupo    Outros**<br/>
rwx                 r-x            r-x  

**Proprietário** - Dono do arquivo ou diretório<br/>
**Grupo** - Usuário ao qual pertence ao grupo, utilizado para dar permisões a outro usuário<br/>
**Outros** - Usuário que não é proprietário e não faz parte do grupo<br/>

**r**    Read (Leitura) - O usuário pode examinar um arquivo ou diretório<br/>
**w**    Write (Escrita) - O usuário pode escrever, alterar o conteúdo do arquivo ou diretório<br/>
**x**    Execution (Execução) - Utilizado quando o arquivo é um programa executável ou script<br/>
**-**    Sem permissão<br/>

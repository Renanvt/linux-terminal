# Comando touch
Muda o registro da data e hora de acesso ou modificação dos arquivos (timestamp).

Também pode criar arquivos vazios

## Sintaxe:
```bash
touch [opções] arquivo
```

## Opções:
**-a**     -Mudar somente a hora de acesso

**-m**    -Mudar somente a hora de modificação

**-t**    timestamp -Em vez de usar a hora atual, usar o timestamp definido no formato AAAAMMDDhhmm.ss
<br/>

```o touch -t``` modifica apenas timestamp de acesso e modificação e não de alteração
**timestamps**:

**Acesso** - A última vez que o arquivo foi lido

**Modificação** - A última vez que o arquivo teve o conteúdo modificado

**Alteração** (change) - A última vez em que metadados do arquivo foram modificados (por ex.: as permissões)

```bash
stat arquivo
```
Ver informações de Acesso, modificação, alteração

# Comando lsmod
Traz informações sobre os módulos carregados atualmente.

Módulo é um drive de algum dispositivo

Vem do arquido /proc/modules

```
lsmod
```
Consulta os módulos que estão instalados

```
lsmod | grep "cdrom"
```

# Comando lsdev
Traz infos sobre o hardware do sistema: IRQ, DMA, E/S  

Instalação:
```
apt-get install procinfo
```

```
yam install procinfo  
```

# Comando hwinfo
Mostra toda configuração de hardware do sistema

Instalação

```
apt-get install hwinfo
```

```
hwinfo --short
```
Listagem curta

# Comando lspci
Traz informações detalhadas sobre os barramentos PCI e seus dispositivos
```
lspci
```

```
lspci -vv
```
modo verboso, traz informações mais detalhadas

# Comando lsusb
Exibe uma listagem dos barramentos USB e seus dispositivos

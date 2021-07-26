# Comando dmesg
Display Message

Quando liga o linux o kernel do linux forneçe uma serie de mensagens que possui informações sobre boot do sistema

As mensagens são armazenadas em um buffer. Podendo ser consultadas mais tarde

Para visualizar essas mensagens utiliza o comando dmesg

O comando dmesg permite visualizar as mensagens do kernel do Linux

Salvar essas informações em um arquivo e comparar com outro sistema posteriormente

```
dmesg > log_mensagens
```

Quando pluga um dispositivo usb o kernel detecta e escreve no buffer

```
dmesg | grep -i "usb"
```

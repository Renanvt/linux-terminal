O cups é um sistema de impressão open-source desenvolvida pela Apple. Para sistemas baseados em unix
```
sudo apt-get install cups
```

```
usermod -a -G lpadmin renanvt
```
Adicionar o usuário ao grupo de adms de impressoras
Line printter Administrator


# Editar o arquivo de configuração
```
cd /etc/cups
```

## Fazer o backup
```
cp cupsd.conf cupsd.conf.old
```

```
sudo vi cupsd.conf
```
```bash
#Indica que o servidor deve ouvir na porta 631 do localhost
#Listen localhost:631
#Libera o acesso do cups a porta 631 para as máquinas da minha rede
Port 631

#Configuração de restrição de acesso ao servidor
<Location />
...
<Location>

#Permitir o acesso das maquinas da rede local
<Location />
Order allow, deny
Allow @local
</Location>

<Location /admin>
Order allow, deny
Allow @local
</Location>

<Location /admin/conf>
AuthType Default
Require user @SYSTEM
Order allow, deny
Allow @local
</Location>
```

# Reiniciar o serviço do cups

```
/etc/init.d/cups restart
```

Acessar o painel adm do cups através do navegador a partir de qualquer máquina local

## ip_maquina:631

```
ifconfig
```
Pegar o ip da máquina

# Guia Administration

Pode editar configurações do servidor
Pode adicionar ou editar impressoras

## Senha de usuário do servidor
Username: root
Password: ****

Add Printer
**Connection**: smb://[ip_windows]/[nome_impressora_compartilhada]

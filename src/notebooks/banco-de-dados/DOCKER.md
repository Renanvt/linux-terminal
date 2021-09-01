```bash
sudo apt-get remove docker docker-engine docker.io containerd runc
```
Desintala versões antigas

```bash
sudo apt-get update
```

```bash
 sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

```bash
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```

```bash
 $ sudo apt-get update
 $ sudo apt-get install docker-ce docker-ce-cli containerd.io
```

# Configurando o docker

```bash
sudo usermod -aG docker $USER
```

```bash
sudo reboot
```
reinicia o computador

```bash
sudo docker run hello-world
```

# Usando o docker

```bash
docker pull
```
baixa a imagem mais recente dos repositórios do docker

```bash
sudo docker pull postgres
```

```bash
mkdir -p $HOME/docker/volumes/postgres
```

```bash
sudo docker run --rm --name pg-docker -e POSTGRES_PASSWORD=docker -d -p 5432:5432 -v $HOME/docker/volumes/postgres:/var/lib/postgresql/data postgres
```

Inicia o postgres via docker. (Antes verifique se o postgres esta parado)

```bash
psql -h localhost -U postgres
```
## A SENHA PADRÃO É: docker
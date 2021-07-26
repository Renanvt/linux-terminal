```
sudo apt install build-essential default-jdk libssl-dev exuberant-ctags ncurses-term ack-grep silversearcher-ag fontconfig imagemagick libmagickwand-dev software-properties-common git vim-gtk3 curl -y
```

Buil-essential tem todo o essencial para fazer o build
jdk -> Compilador do java mais novo

```
sudo apt -y install postgresql-contrib redis-server libhiredis-dev memcached libmemcached-dev
```
Instala o banco de dados relacional, nosql e cache

```
git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.8.0
```
Instala o gerenciador de versões

```
git clone https://github.com/asdf-vm/asdf.git ~/.asdf
cd ~/.asdf
git checkout "$(git describe --abbrev=0 --tags)"
```

```
echo -e '\n. $HOME/.asdf/completions/asdf.bash' >> ~/.bashrc
```

```
echo -e '\n. $HOME/.asdf/asdf.sh' >> ~/.bashrc
```
asdf - Gerenciador de versão universal

```
sudo apt install linux-headers-$(uname -r) build-essential

sudo apt-get install libreadline-dev

sudo apt-get install zlib1g-dev curl
```
Instalar plugins para as linguagens

```
asdf plugin-add postgres
```
Instala o plugin do postgres

```
asdf plugin-add spring-boot https://github.com/joschi/asdf-spring-boot
```
Instala o plugin do spring boot

```
asdf plugin-add java https://github.com/halcyon/asdf-java.git
```
Instala o plugin do java

```
asdf plugin-add nodejs https://github.com/asdf-vm/asdf-nodejs.git
```

```
bash -c '${ASDF_DATA_DIR:=$HOME/.asdf}/plugins/nodejs/bin/import-release-team-keyring'
```
Instala o plugin do node

```
npm i -g npm
```
Instala o gerenciador de pacotes npm

```
asdf plugin-add golang https://github.com/kennyp/asdf-golang.git
```
Instala o plugin do golang

```
asdf plugin-add ruby https://github.com/asdf-vm/asdf-ruby.git
```
Instala o plugin do ruby

```
sudo apt-get -y install build-essential autoconf m4 libncurses5-dev libwxgtk3.0-gtk3-dev libgl1-mesa-dev libglu1-mesa-dev libpng-dev libssh-dev unixodbc-dev xsltproc fop libxml2-utils libncurses-dev openjdk-11-jdk
```

```
asdf plugin add erlang https://github.com/asdf-vm/asdf-erlang.git
```
Instala o plugin do erlang

```
asdf plugin-add elixir https://github.com/asdf-vm/asdf-elixir.git
```
Instalar o plugin do Elixir

```
asdf plugin-add kotlin https://github.com/asdf-community/asdf-kotlin.git
```
Instala o plugin do Kotlin

```
asdf plugin-add rust https://github.com/code-lever/asdf-rust.git
```
Instala o plugin do Rust

```
asdf plugin-add crystal https://github.com/asdf-community/asdf-crystal.git
```
Instala o plugin do Crystal

```
asdf plugin-list
```
Lista todos os plugins instalados

```
asdf list-all nodejs
```
Lista todas as versões do plugin nodejs

```
asdf list postgres
```
Mostra a lista de versões instaladas do postgres

```
asdf install nodejs  14.15.4
```
Instala a versão 14.15.4 do nodejs

```
asdf global ruby 2.7.2
```
Declara que queremos usar a versão especificada

```
ruby -v
```
Verifica a versão do ruby

```
. ~/.asdf/plugins/java/set-java-home.bash
```

```
. ~/.asdf/plugins/java/set-java-home.fish
```
Instala o javahome

```
postgres --version
```
Verifica a versão do postgres

```
mkadir old_legacy
cd old_legacy/
asdf local ruby 2.4.4
```
Só dentro da pasta old_legacy escolhe o ruby com a versão 2.4.4

```
asdf plugin-update --all
```
Atualizar os plugins do asdf

```
asdf update
```
Atualiza o asdf

```
sudo apt install npm
```
Instalar o npm

```
asdf rshims
```
Recria os reshims no caminho /home/user/.asdf/shims.
Shims são como proxys para os binários de verdade

```
dpkg -L software-properties-common
```
Lista tudo que tem no pacote software-properties-common

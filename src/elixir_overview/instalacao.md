# Instalação

Para podermos de fato começar a utilizar o elixir, precisamos primeiro instalar ou utilizar um docker, mas no nosso caso, iremos instalar mesmo.

No momento em que estou escrevendo este livro, estamos na versão 1.14.4 do elixir e os exemplos são baseados no sistema operacional Ubuntu 20.04 LTS.

Neste caso, irei instalar utilizando o ASDF, mas você pode ver [outras maneiras de instalar](https://elixir-lang.org/install.html)

## ASDF
O [ASDF](https://asdf-vm.com/) é um gereniador de versões muito utilizado para gerenciar as versões do Ruby, NodeJs, Elixir entre outros.

1. Instalando dependências
```bash
sudo apt install curl git
```

2. Download do asdf
```bash
git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.12.0
```

3. Instalando asdf
```bash
. "$HOME/.asdf/asdf.sh"
```

Caso tenha ficado alguma dúvida, o link para instalação do ASDF você pode ver [aqui](https://asdf-vm.com/guide/getting-started.html)

## Erlang
Com o asdf instalado, poderemos instalar o erlang e elixir.
Ter o Erlang instalado é um pré-requisito para instalar o elixir, então vamos seguir instalando o Erlang.

1. Instalação de dependências
```bash
sudo apt-get -y install build-essential autoconf m4 libncurses5-dev libwxgtk3.0-gtk3-dev libwxgtk-webview3.0-gtk3-dev libgl1-mesa-dev libglu1-mesa-dev libpng-dev libssh-dev unixodbc-dev xsltproc fop libxml2-utils libncurses-dev openjdk-11-jdk
```

2. Adicionar plugin do erlang no asdf
```bash
asdf plugin add erlang https://github.com/asdf-vm/asdf-erlang.git
```

3. Instalar o erlang na versão 25.3.1
```bash
asdf install erlang 25.3.1
```

Caso tenha ficado alguma dúvida, o link para instalação do Erlang via asdf você pode ver [aqui](https://github.com/asdf-vm/asdf-erlang)

## Elixir

1. Adicionar plugin do elixir no asdf
```bash
asdf plugin-add elixir https://github.com/asdf-vm/asdf-elixir.git
```

2. Instalar o elixir na versão 1.14.4-otp-25
```bash
asdf install elixir 1.14.4-otp-25   
```

Caso tenha ficado alguma dúvida, o link para instalação do Elixir via asdf você pode ver [aqui](https://github.com/asdf-vm/asdf-elixir)



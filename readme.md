# Instalação do Docker Desktop no Linux Ubuntu 22.04
## A instalação foi feita em uma máquima virtual usando o VirualBox
### VirtualBox
    VirtualBox é um produto de virtualização da Oracle para expandir os recursos de utilização do seu computador. Mas, o que é virtualização? Virtualização trata-se da criação de um ou mais ambientes virtuais dentro de um mesmo computador físico, que funcionam de maneiras independentes.
    

    https://download.virtualbox.org/virtualbox/6.1.36/VirtualBox-6.1.36-152435-Win.exe


    ### Aṕos a instalação e criação da máquina virtual para o sistema Ubuntu,você deve acessar as configurações da máquina, ir ao item sistema, clicar na guia processador e habilitar "Habilitar VT-x/AMS-V Aninhado"

### Linux Ubuntu 22.04
    O Ubuntu é um sistema dedicado para o desktop que permite muitas facilidades! Como resultado, ele não apenas apresenta uma interface amigável como ainda é gratuito. Além disso, seu uso permite o apoio de um suporte profissional em uma das comunidades mais robustas do Linux do mundo.

    https://ubuntu.com/download/desktop

### Docker 
    Docker é um conjunto de produtos de plataforma como serviço que usam virtualização de nível de sistema operacional para entregar software em pacotes chamados contêineres. Os contêineres são isolados uns dos outros e agrupam seus próprios softwares, bibliotecas e arquivos de configuração.

## Configuração e instalação de ambiente

### Pós-Instalação do Linux
    Após a instalação do Linux Ubuntu 22.04, você deve executar alguns comandos para utilizar o sistema e deixa-lo preparado para instalação do Docker.

### Atualização dos pacotes
    ```console
    $ sudo apt update
    ```

### Atulização do sistema
    ```console
    $ sudo apt upgrade
    ```

### Reinicie o sistema
    ```console
    $ reboot
    ```

### instalação do DOcker Desktop
    Download do Docker Desktop
    https://desktop.docker.com/linux/main/amd64/docker-desktop-4.10.1-amd64.deb?utm_source=docker&utm_medium=webreferral&utm_campaign=docs-driven-download-linux-amd64

    Na pasta(diretório) download localize o arquivo docker-desktop-4.10.1-amd64.deb e assim que você pode instalar de duas maneiras, sendo:
    1º- Clicar com o botão direito do mouse sobre o arquivo e escolher o Software Install;

    2º- Abrir o terminal e ir até a pasta (diretório) download e executar o comando de instalação:
    ```console
    $ sudo apt install ./docker-desktop-4.10.1-amd64.deb
    ```

### Caso retorne uma mensagem de erro referente ao Docker-ce e/ou Docker-cli, execute os comandos abaixo:
    ```console
        $ sudo apt-get update

        $ sudo apt-get install \
            ca-certificates \
            curl \
            gnupg \
            lsb-release
    ```
    Adicionar as chaves de GPG oficiais do docker
    ```console
        $ sudo mkdir -p /etc/apt/keyrings

        $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
    ```
    use os comandos abaixo para carregar o repositório de pacotes
     ```console
        $ echo \
        "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    ```
### Instalação do Docker Engine
    ```console
    $ sudo apt-get update
 
    $ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
    ```
### Após a instalação das dependências você deve executar o comando de instalação do Docker Desktop
    ```console
    $ sudo apt install ./docker-desktop-4.10.1-amd64.deb
    ```
## Instalamdo a Imagem e o Container de mySQL no Docker
### Vamos usar o volume neste exemplo
    Crie uma pasta(diretótio) chamada data_docker, no home do usuário, execute o seguinte comando:
        ```console
        $ docker run --name servidor-mysql -v ~/data_docker:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456 -d mysql:8.0.29
        ```
    Agora, abra o docker-desktop e veja o seu container rodando.



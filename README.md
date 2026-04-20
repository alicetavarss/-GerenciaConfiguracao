
 ## Guia de configuração de acesso remoto (SSH) e Firewall (UFW) num sistema Linux.

 ### Este guia detalha como criei e preparei um servidor Ubuntu 24.04 dentro do Docker, incluindo a ativação e verificação de segurança do Firewall.


 
### Passo 1: Criando o Container

Para iniciar, criamos o container com os privilégios necessários para gerenciar serviços de sistema.
Bash

```docker run -it --privileged --name GerenciaConfiguracao ubuntu:24.04 bash```


### Passo 2: Atualizando o Sistema

Sempre atualize a lista de pacotes e aplique as correções antes de instalar novos softwares.
Bash

``apt-get update
apt-get upgrade -y``

### Passo 3: Instalando o SSH e o Firewall

Instalamos o servidor para acesso remoto e o ufw para proteção de rede.
Bash

``apt-get install -y openssh-server ufw``


### Passo 4: Gerenciando o Firewall (UFW)

Agora que o firewall está instalado, precisamos garantir que ele esteja ativo e funcionando.

Para ativar o Firewall:

``ufw enable`` 

(O UFW perguntará se deseja continuar. Digite y e dê Enter).

Para verificar o status do Firewall:

``ufw status``


(Se aparecer "Status: active", significa que sua proteção está ligada.)

Para liberar a porta do SSH (essencial para não perder o acesso):


``ufw allow ssh``

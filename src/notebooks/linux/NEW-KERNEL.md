O kernel é o componente principal de um sistema operacional Linux e a interface central entre o hardware e os processos executados por um computador. Ele estabelece a comunicação entre ambos, gerenciando recursos com a maior eficiência possível.

A palavra "kernel" em inglês significa grão (uma semente revestida por uma casca dura) e é seguindo essa analogia que ele existe dentro do sistema operacional e controla todas as principais funções do hardware, seja ele um smartphone, um laptop, um servidor ou qualquer outro tipo de computador.


# O que o kernel faz?

O kernel tem quatro funções:

1. **Gerenciamento da memória**: ele monitora o volume de memória utilizado para armazenar o que (arquivos, dados etc.) e onde (ambiente).<br/>
2. **Gerenciamento de processos**: ele determina quais processos podem usar a unidade central de processamento (CPU), quando e por quanto tempo.<br/>
3. **Drivers de dispositivos**: ele atua como intermediário/intérprete entre o hardware e os processos.<br/>
4. **Chamadas do sistema e segurança**: ele recebe solicitações dos processos para a execução de serviços.<br/>

O kernel, se implementado corretamente, é imperceptível para o usuário. Ele funciona por conta próprio em um mundinho chamado espaço do kernel, onde aloca a memória e monitora onde todas as coisas são armazenadas. O que o usuário vê, por exemplo, os navegadores da web e **arquivos**, é chamado de espaço do usuário. As aplicações interagem com o kernel por meio de uma interface de chamadas do sistema (SCI).

Pense da seguinte forma: o kernel é como um assistente pessoal muito ocupado que trabalha para um executivo poderoso (o hardware). É trabalho do assistente transmitir as mensagens e solicitações (processos) dos funcionários e do público (usuários) para o executivo, lembrar o que está armazenado e onde (memória), e determinar quem tem acesso ao executivo, em que horário e por quanto tempo.


# Onde o kernel se encaixa no sistema operacional?

Para contextualizar melhor o local do kernel, imagine que a máquina Linux seja formada por três camadas:

1. **Hardware**: é a máquina física, a base do sistema composta de memória (RAM) e unidade central de processamento (CPU), além de alguns dispositivos de entrada e saída (E/S), como disco de armazenamento, componentes de rede e placa gráfica. A CPU executa os cálculos e faz leituras/gravações na memória.<br/>
2. **Kernel do Linux**: é o núcleo do sistema operacional (está bem no meio). Trata-se do software que reside na memória e instrui a CPU sobre o que fazer.<br/>
3. **Processos do usuário**: são os programas em execução gerenciados pelo kernel. O conjunto de processos do usuário formam o espaço do usuário. Os processos do usuários também são chamados apenas de processos. Além disso, o kernel estabelece a comunicação entre esses processos e os servidores, o que é conhecido como comunicação entre processos (IPC).


O código é executado pelo sistema nas CPUs em dois modos: modo do kernel ou modo do usuário. Quando executado no modo do kernel, o código tem acesso irrestrito ao hardware. Já no modo do usuário, o acesso fica restrito à CPU e à memória na SCI. Há uma separação semelhante na memória: espaço do kernel e espaço do usuário. Esses dois pequenos detalhes formam a base de algumas operações complicadas, como a separação de privilégios para fins de **segurança**, **criação de containers** e **uso de máquinas virtuais**.

Isso também significa que se um processo falhar no modo do usuário, o dano será limitado e poderá ser recuperado pelo kernel. No entanto, como ele tem acesso à memória e ao processador, uma falha de processo do kernel pode travar o sistema inteiro. Mas por haver medidas de segurança a postos e permissões necessárias para cruzar certos limites, as falhas nos processos do usuário normalmente não causam grandes problemas.


1. Fazer BACKUP dos arquivos antes de instalar um novo Kernel

```
uname -r
```
Verifica a versão atual do kernel

```
apt-cache search linux-image
```
Verificar as imagens de kernel disponível para essa distribuição

```
apt-get install [imagem_escolhida]
```
Instala um novo kernel

```
shutdown -r now
```
Reinicia o computador

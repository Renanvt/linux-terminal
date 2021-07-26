# Drivers de dispositivos

Um driver de dispositivo é uma parte do Kernel do Linux que controla um dispositivo, como um terminal, disco rígido ou uma impressora.
O sistema operacional em si não sabe como se comunicar diretamente com a maior parte dos dispositivos de hardware. Para essa tarefa são usados os drivers de dispositivos que são pequenos programas utilizados como interface entre o S.O e o dispositivo de hardware

# Diretório /sys

Pseudo-sistema de arquivos de dispositivos.
Função: facilitar a troca de informações entre os programas que rodam no espaço do kernel, como os drivers, como os programas que rodam no espaço do usuário (aplicações). Por exemplo quando um aplicativo precisa acessar um dispositivo de hardware

Quando um dispositivo é adicionado ao sistema, o kernel cria um nome de dispositivo em /sys, e notifica o utilitário **udev**, o qual gerencia os nomes de dispositivos dinamicamente, criando então um arquivo de dispositivo, geralmente em **/dev** (ou o remove)

# Diretório /sys - alguns subdiretórios

Módulo é uma pequeno software que você pode plugar ou desplugar do kernel do linux

**/sys/bus** - Barramentos de dados do sistema

**/sys/module** - Módulos carregados no kernel

**/sys/devices** - Todos os dispositivos conectados

**/sys/block** - Dispositivos de bloco, como HDs
<br/>

# Módulos carregáveis no Kernel

Módulos são arquivos-objeto, parte do kernel, que são vinculados a ele em tempo de execução
Os módulos podem ser inseridos e removidos em um kernel em execução a qualquer tempo, exceto quando em uso
Drivers podem ser inseridos na forma de módulos do Kernel
Os arquivos de drivers geralmente terminal com a extensão **.ko (ou .o)** e são armazenados em subdiretórios dentro de **/lib/modules**

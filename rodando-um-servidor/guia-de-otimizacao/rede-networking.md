# Rede - Networking

### Rede - Networking

#### Arquivo: [server.properties](https://minecraft.fandom.com/wiki/Server.properties)

**Configuração: network-compression-threshold**

`Bom valor inicial: 256`

Isso permite que você defina o limite para o tamanho de um pacote antes que o servidor tente compactá-lo. Defini-lo mais alto pode economizar alguns recursos da CPU ao custo da largura de banda e defini-lo como -1 o desativa. Definir esse valor mais alto também pode prejudicar clientes com conexões de rede mais lentas. Se o seu servidor estiver em uma rede com um proxy ou na mesma máquina (com menos de 2 ms de ping), desabilitar isso (-1) será benéfico, pois as velocidades internas da rede geralmente podem lidar com o tráfego descompactado adicional.

#### Arquivo: [purpur.yml](https://purpurmc.org/docs/Configuration/)

**Configuração: use-alternate-keepalive**

`Bom valor inicial: true`

Você pode ativar o sistema de manutenção de atividade alternativo de Purpur para que jogadores com conexão ruim não percam o tempo limite com tanta frequência. Tem incompatibilidade conhecida com TCPShield.

> Habilitar isso envia um pacote keepalive uma vez por segundo para um jogador, e só desconectará o jogador se nenhum deles for respondido em 30 segundos. Responder a qualquer um deles em qualquer ordem manterá o jogador conectado. Diferente da configuração vanilla, que desconectará o jogador se um pacote não foi respondido.\
> \~ [https://purpurmc.org/docs/Configuration/#use-alternate-keepalive](https://purpurmc.org/docs/Configuration/#use-alternate-keepalive)

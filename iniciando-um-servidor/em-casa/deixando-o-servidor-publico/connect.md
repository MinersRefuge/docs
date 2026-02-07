# Connect

O Connect é um plugin para Minecraft que conecta servidores à Rede Global Connect, permitindo anunciá-los em vários canais para atrair mais jogadores. Ele mantém a propriedade total do servidor com você, mesmo oferecendo descoberta fácil na lista de servidores do jogo. Além disso, torna servidores localhost acessíveis publicamente e fornece um domínio gratuito.

Nesse tutorial, você aprenderá a utilizar o plugin Connect para deixar o seu servidor de Minecraft hospedado em seu computador acessível publicamente pela internet. Para isso, siga os passos abaixo:

Antes de seguir esse tutorial, tenha certeza de que você já tem o um servidor Localhost e com o software que suporta [Plugins](../../softwares-de-servidor/plugins.md).

### 1. Baixando o plugin Connect

Os passos de instalação são os mesmos de qualquer outro plugin do Minecraft (baixe o jar, coloque-o na pasta de plugins e inicie o servidor) . Baixe o plugin Connect aqui mesmo!

| **Plugin Spigot/PaperMC** | 
| :------: | 
|    [connect-spigot.jar](https://github.com/minekube/connect-java/releases/download/latest/connect-spigot.jar)    |

### 2. Desabilitando **enforce secure player profiles** <span style="color:red">*</span>

Desde o Minecraft 1.19 o <code>enforce-secure-profile</code> A propriedade foi introduzida. Jogadores que se conectarem ao seu servidor através da Rede de Conexão não poderão se conectar se esta configuração estiver habilitada. É seguro desabilitar esta configuração, pois ela afeta apenas as mensagens de bate-papo.

**server.properties**
```properties
enforce-secure-profile=false

# Se você desabilitar o modo online, o enforce-secure-profile não terá efeito
online-mode=true
```


### 3. Entrando no seu servidor

Cada servidor tem um nome de endpoint único, que funciona como o endereço (domínio) que os jogadores usam para entrar.

Você pode escolher esse nome mas, se deixar em branco, o Connect vai gerar automaticamente um nome temporário usando o Serviço de Nomes Aleatórios.

**plugins/conectar/config.yml**
```properties
endpoint: your-server-name
```
**Gate config.yml**
```properties
connect:
  name: your-server-name
```

### 4. Entrando ao domínio público fornecido gratuitamente

Depois de instalar o plugin Connect e iniciar seu servidor, você verá o domínio público gratuito para seu servidor que se parece com <code>(endpoint).play.minekube.net</code>

**Console do Servidor**
```properties
[connect] Enabling connect vX.Y.Z
[connect] Enpoint name: live-beru
[connect] Your public address: live-beru.play.minekube.net
```

As solicitações de ping também são espelhadas no servidor de endpoint.
<figure><img src="../../../.gitbook/assets/terminal-log.cxer63TY.png" alt=""><figcaption></figcaption></figure>

#### Entrando pelo Hub do Navegador

Os jogadores também podem descobrir seu servidor no Hub do navegador do jogo em <code>minekube.net</code> e pode se juntar às interfaces de usuário do jogo ou ao <code>/browser join</code> <your-server-name>comando.
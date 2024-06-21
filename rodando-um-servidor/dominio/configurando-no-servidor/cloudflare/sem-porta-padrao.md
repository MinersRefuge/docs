# Sem porta padrão

Entre na aba de Websites da Cloudflare, depois clique no domínio no qual deseja utilizar.

Para essa configuração será necessário criar dois registros.

Nas configurações DNS do seu domínio (Lado esquerdo), crie um novo registro com as seguintes informações, esse registro será usado apenas internamente, mas poderá ser usado caso tiver jogadores bedrock no seu servidor:

* **Tipo**: A
* **Nome:** @ se não quiser subdomínio, se quiser um, escreva o subdomínio (Ex: jogar), isso se tiver jogadores Bedrock no seu servidor. Caso não tenha jogadores Bedrock, pode bater a cabeça no teclado que oq sair está valendo.
* **IPV4:** Coloque o endereço IPV4 do servidor
* **Proxy Status:** Deixe como DNS Only (Nuvem cinza)
* **TTL:** Auto

<figure><img src="../../../../.gitbook/assets/image (47).png" alt=""><figcaption><p>Exemplo com a configuração citada a cima</p></figcaption></figure>

Crie um novo registro, esse registro será usado para os jogadores se conectarem:

* **Tipo**: SRV
* **Nome:** @ se não quiser subdomínio, caso contrário, escreva o subdomínio (Ex: jogar)
* **Serviço**: Coloque `_minecraft`
* **Protoclo:** Selecione TCP
* **TTL:** Auto
* **Prioridade:** 0
* **Peso:** 0
* **Porta:** Porta do seu servidor (Java)
* **Alvo:** O registro que criou anteriormente

<figure><img src="../../../../.gitbook/assets/image (46).png" alt=""><figcaption><p>Exemplo com a configuração citada a cima</p></figcaption></figure>

Os dois registros estão com o mesmo nome neste exemplo, mas não haverá problema nesse caso por serem de tipos diferentes, os jogadores tanto Bedrock quanto java poderão entrar no servidor usando o mesmo nome de domínio.

Entretanto, os jogadores Bedrock ainda precisarão colocar a porta do seu servidor quando se conectarem

Leve em consideração que mudanças DNS podem demorar até 24 horas para fazerem efeito globalmente, entretanto, Cloudflare é conhecida por ser rápida para isso, e pode levar apenas alguns minutos para alguns provedores de internet atualizarem.\
Para conferir se houve as mudanças corretas, pode utilizar sites como [dnschecker](https://dnschecker.org/) e [mcsrvstatus](https://mcsrvstat.us/).

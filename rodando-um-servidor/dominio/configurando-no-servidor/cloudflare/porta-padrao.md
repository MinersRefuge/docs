# Porta padrão

Entre na aba de Websites da Cloudflare, depois clique no domínio no qual deseja utilizar.

Nas configurações DNS do seu domínio (Lado esquerdo), crie um novo registro com as seguintes informações:

* **Tipo**: A
* **Nome:** @ se não quiser subdomínio, caso contrário, escreva o subdomínio (Ex: jogar)
* **IPV4:** Coloque o endereço IPV4 do servidor
* **Proxy Status:** Deixe como DNS Only (Nuvem cinza)
* **TTL:** Auto

<figure><img src="../../../../.gitbook/assets/image (45).png" alt=""><figcaption><p>Exemplo com a configuração citada a cima</p></figcaption></figure>

Leve em consideração que mudanças DNS podem demorar até 24 horas para fazerem efeito globalmente, entretanto, Cloudflare é conhecida por ser rápida para isso, e pode levar apenas alguns minutos para alguns provedores de internet atualizarem.\
Para conferir se houve as mudanças corretas, pode utilizar sites como [dnschecker](https://dnschecker.org/) e [mcsrvstatus](https://mcsrvstat.us/).

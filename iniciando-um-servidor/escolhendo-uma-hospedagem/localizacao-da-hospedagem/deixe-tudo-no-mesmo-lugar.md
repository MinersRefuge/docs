# Deixe tudo no mesmo lugar

Muitas pessoas, quando estão fazendo uma network com vários modos de jogo, pensam em deixar os que precisam de uma baixa latência em uma localização, e os que não precisam em outra localização, entretanto, isso não funciona e não deve ser feito de nenhum modo.

Isso é pela maneira que o trafego do Minecraft funciona dentro de uma network:

**Cliente > Proxy > Backend**

Isso é, o tráfego do cliente passa pelo proxy e vai até o backend, para voltar ao cliente ele vem do backend, vai para o proxy e depois ao cliente.\
Ou seja, todo o trafego do seu servidor **sempre irá passar pelo proxy,** busque sempre ter a menor latência possível entre o proxy e o backend.

Também, a segurança poderá estar degradada, é muito mais seguro apenas o proxy estar disponível publicamente e os backend apenas poder ser acessado dentro da mesma rede, assim, impedindo que ataques externos sejam feitos, tendo menos pontos fracos em seu servidor.

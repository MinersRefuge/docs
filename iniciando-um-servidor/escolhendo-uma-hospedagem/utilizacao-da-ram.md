# Utilização da ram

Caso seja apenas um servidor, não será uma rede, é mais fácil de definir quanto precisará.\
Em qualquer versão acima da 1.13 oconsenso geral é o mínimo de 4GB de ram, com o recomendado sendo 6GB de ram.\
Isto por causa de algo chamado "The Flattering" e as grandes mudanças que a mojang apresentou nas versões 1.13 e 1.14

<details>

<summary>"The Flattering" e 1.13/1.14</summary>

**`1.12 -> 1.13`** foi uma grande mudança por causa do "[Flattering](https://minecraft.fandom.com/wiki/Java\_Edition\_1.13/Flattening)". A Mojang também começou a trabalhar para tornar a geração de chunks async, mas md\_5 reverteu suas alterações para sincronizá-los novamente. O desempenho da 1.13 não era bom até que a Aikar fez sua própria implementação de chunks async que era muito mais rápido que a 1.12 (você poderia gerar novas chunks no sistema da 1.13 da Aikar mais rápido do que a 1.12 poderia carregar chunks pré-geradas).

**`1.13 -> 1.14`** foi o maior caos porque Mojang reverteu as chunks async e decidiu refazer todo o sistema de geração de chunks. Isso foi completamente fracassado porque a Microsoft os pressionou a trabalhar em Villagers/Pillagers para obter paridade de recursos com Bedrock. Eles não tiveram tempo suficiente para fazer as duas coisas, então ambas acabaram falhando. Como os ticks de entidade são baseados em ticks de chunks, todo o jogo foi terrivelmente lento.

Cada atualização desde então tem sido uma mistura de novos blocos/entidades e correções de desempenho daquela bagunça 1.14. Infelizmente, nem tudo pode ser atualizações de desempenho porque a Microsoft ainda oferece paridade de recursos com o Bedrock, então o tempo dos desenvolvedores ainda está dividido.

</details>

Agora sendo uma network, precisará contar e somar de todos os servidores, mas não superestime quanto precisará.

* O proxy não fará muito uso de ram, limite para 1GB inicialmente
* Os lobbies também não farão, 2GB servirá sem problemas
* Backend dependerá do que for, mas abaixo da 1.13 4GB pode servir, e acima busque por 6GB no mínimo.

**Observação**: Esses valores não servirão para todos, estão aqui apenas como uma base. Recomenda-se primeiro testar com um valor baixo e ir aumentando conforme necessário.

### Garbage collector

O seu servidor tem algo chamado "Garbage Collector", que basicamente "limpa" a ram de recursos não mais utilizados periodicamente, fazendo isso a cada alguns segundos, entretanto, ele só vai ser ativado quando atingir o limite de RAM que lhe foi alocado, e essa RAM **não** será retornada para o sistema.

A JVM não retorna memória não utilizada ao sistema operacional. Isso é intencional, e se você observasse o uso de RAM do seu servidor a partir de um monitor do sistema ou pelo painel de sua hospedagem, você o veria subir continuamente até atingir a quantidade máxima de RAM que pode ser usada (o valor da flag Xmx). Portanto, nem toda a RAM mostrada como "usada" pelos monitores do sistema está realmente sendo usada, e grande parte dela geralmente fica parada esperando que o servidor a utilize.\

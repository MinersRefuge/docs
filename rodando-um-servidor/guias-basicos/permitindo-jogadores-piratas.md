---
description: 'Última vez que esse guia foi atualizado: 30/12/2023'
---

# Permitindo jogadores piratas

Permitir jogadores piratas no seu servidor (Também conhecidos como jogadores offline) é de muito desejo por alguns donos de servidores, esse modo foi feito essencialmente para jogar em LAN e para testes de servidor, mas nunca para ser usado em produção.

Então, tem alguns pontos que devem ser notados antes de fazer essa alteração:

* Perderá a conexão com os servidores da Mojang, significando que não terá mais autenticação de nicks, **qualquer pessoa poderá entrar com qualquer nick**, e também que as skins não mais funcionarão corretamente, estando normalmente com Steve ou Alex.
* Caso já tenham players que estavam jogando no servidor, **todos perderão os itens**, pois os UUIDs serão alteradores do v4 para o v3, juntamente com as conquistas, XP, pets, e qualquer outro elemento que esteja linkado com o player originalmente.
* **Poderá perder o suporte de muitos plugins**, donos e developers normalmente se recusam a dar qualquer suporte para donos de servidores com essa configuração, muitas leves podendo levar ao seu **banimento da comunidade de suporte**.
* **Poderá perder o suporte de sua hospedagem**, muitas hospedagens se recusarão a dar suporte mais específico para clientes que usam essa configuração, tanto por estar **contra os termos de serviço da Mojang**, **umas darão apenas o suporte mínimo**, outras relataram em que **não irão lhe querer mais como um cliente**.

Caso decida mesmo assim fazer essa alteração e permitir jogadores piratas/offline entrar em seu servidor, siga esses passos:

1. Encontre o arquivo `server.properties`, estará na pasta raiz/root do seu servidor dentro do painel.
2. Procure a linha que esteja com `online-mode=true` (Normalmente a linha 23, porém pode variar dependendo da versão)
3. Altere o `online-mode=true` para `online-mode=false` e reinicie o seu servidor

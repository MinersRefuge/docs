---
description: >-
  Essa é apenas a tradução do blog do me4502 explicando os motivos do comando
  /reload ser fatal e por que ele é inseguro
---

# Tradução do blog do me4502

## [Link original para o blog](https://madelinemiller.dev/blog/problem-with-reload/)

### Por que ele existe?

O objetivo era permitir que os proprietários do servidor recarregassem os arquivos de configuração dos plugins e do próprio servidor de forma rápida e fácil. No entanto, para facilitar o trabalho dos desenvolvedores de plugins, o comando acabou tendo uma falha fatal que o tornava inseguro de usar. Essa decisão foi diferente de plataformas de servidor anteriores, como hMod, que se comportavam de maneira muito mais controlada. A equipe do Bukkit decidiu que o comando reload deveria desabilitar todos os plugins e tentar ativá-los novamente. Essencialmente, simulando o desligamento e a inicialização do servidor enquanto ainda está em execução.

### Por que ele é quebrado e inseguro?

Como o Java não fornece uma maneira segura ou com suporte para descarregar ou recarregar o código que já está carregado, isso começou a causar alguns problemas e erros sutis. Carregar tudo de novo em alguns casos causava conflitos entre o código antigo e o novo código do reload. Esse problema é especialmente grave ao substituir arquivos jar do plugin. Devido a isso, Spigot e Paper nunca recomendaram o uso do comando reload. A aversão significativa ao comando reload devido aos[ problemas que ele causava já era evidente em 2011](https://bukkit.org/threads/petition-to-remove-the-reload-command.43212/), logo após o início do Bukkit. Desde então, esses problemas pioraram significativamente.

À medida que o Minecraft evoluiu, o que precisava ser recarregado tornou-se muito mais complicado, até que o conceito de recarregar se tornou totalmente inviável. Cada atualização recente viu o comando recarregar causar mais problemas. No momento, ninguém deve usar o comando <mark style="color:yellow;">`/reload`</mark> em nenhuma circunstância. Ele causa instabilidades significativas no Minecraft, Bukkit, Spigot, Paper e quase todos os plugins que usam a API do Bukkit. Atualmente, uma ação tão simples quanto verificar as permissões do jogador pode causar problemas após um reload. Se um plugin falhar após uma recarga, (provavelmente) não é culpa do plugin, mas sim um sintoma do comando de recarregamento fundamentalmente quebrado. Ao contrário dos primeiros dias de 2011, os plugins não podem apenas fazer alterações para oferecer melhor suporte ao comando reload.

### **Então, o que deve ser usado em vez disso?**

Ao adicionar novos plugins, atualizar um plugin existente ou remover um plugin, você sempre deve reiniciar o servidor. O recarregamento pode e deixará seu servidor em um estado instável. Ao fazer alterações na configuração de um plugin, no entanto, a maioria dos plugins fornece um comando para recarregar sua configuração. Por exemplo, <mark style="color:yellow;">`/cb reload`</mark> recarregará os arquivos de configuração do CraftBook. Esses comandos não sofrem os mesmos problemas que o comando <mark style="color:yellow;">`/reload`</mark>. Se um plugin não tiver um desses comandos, peça para adicionar um ou apenas reinicie o servidor.

Se você substituiu algum arquivo jar, recarregar o servidor **criará problemas**, mesmo que você não perceba. O comando <mark style="color:yellow;">`/reload`</mark> é **sempre** inseguro e sujeito a erros.

### Hotswapping como desenvolvedor

Se você é um desenvolvedor e usa <mark style="color:yellow;">`/reload`</mark> para testar seus plugins mais rapidamente, isso também é uma má ideia. Fazer alterações de código com frequência e recarregar aumentará substancialmente o problema. Em vez disso, você pode usar com segurança um hotswapper de código, como o depurador IntelliJ, para aplicar com segurança as alterações de código do seu IDE diretamente a um servidor em execução. Isso é mais conveniente do que construir e recarregar e substancialmente mais seguro.

### E sobre o PlugMan?

Usar plugins como o PlugMan para ativar ou desativar plugins ainda é problemático. Ele não apenas atinge os mesmos problemas acima, mas também quebra as expectativas que os plugins têm sobre o servidor. Como o Bukkit não foi projetado para que os plugins sejam carregados sozinhos, isso pode causar problemas quando os plugins estiverem em um estado inválido. Além disso, é comum que os plugins assumam que o servidor acabou de iniciar quando o plugin é carregado, portanto, o plugin pode estar funcionando com dados incorretos se for iniciado posteriormente.

### E quanto a outras plataformas como Sponge ou Minecraft Vanilla?

Este aviso não se aplica ao comando reload do Sponge. O comando Sponge reload não faz o que o Bukkit faz e, em vez disso, envia um evento para os plugins informando que um recarregamento foi solicitado. É então responsabilidade do plugin recarregar as configurações.

O comando vanilla Minecraft reload para pacotes de dados também é seguro. Se você quiser usar o comando Minecraft <mark style="color:yellow;">`/reload`</mark> para recarregar pacotes de dados em servidores baseados em Bukkit, você pode usar com segurança <mark style="color:yellow;">`/minecraft:reload`</mark>.

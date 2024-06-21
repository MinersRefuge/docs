---
description: >-
  Alguns tipos de plugins que são "Bom de mais para ser verdade" e que causarão
  problemas, de uma forma ou outra.
---

# Plugins

### Plugins removendo itens do solo

Absolutamente desnecessário, pois eles podem ser substituídos por <mark style="color:yellow;">`merge-radius`</mark> e <mark style="color:yellow;">`alt-item-despawn-rate`</mark> e, francamente, são menos configuráveis ​​do que as configurações básicas do servidor. Eles tendem a usar mais recursos para escanear e remover itens do que não remover nenhum item.

### Plugins para stack de mobs

É realmente difícil justificar o uso de um. Stackar entidades geradas naturalmente causa mais lag do que não empilhá-las devido ao servidor constantemente tentar gerar mais mobs. O único caso de uso "aceitável" é para spawners em servidores com uma grande quantidade de spawners.

> Digamos que na vida real você tenha a tarefa de manter 50 árvores (faça de conta que essas são suas entidades no jogo) em seu quintal, mas algum idiota (clearlagg) aparece a cada 5 minutos e derruba todas. É seu trabalho garantir que sempre haja 50 árvores plantadas no MÍNIMO. Então você tem que ir plantar mais. Então o Sr. Asshat aparece 5 minutos depois e os corta novamente (enxágue e repita).
>
> O mesmo pode ser dito sobre qualquer plug-in de empilhamento de mob. imagine que você tem que manter 50 árvores em sua terra, mas algum idiota (mob stacker) exclui 49 delas e coloca uma placa naquela 1 árvore restante que diz "x50". Há realmente apenas 1 árvore lá, e você ainda tem que manter um MÍNIMO de 50, então você planta mais 49.

### Plugins habilitando/desabilitando outros plugins

Qualquer coisa que habilite ou desabilite plugins em tempo de execução é extremamente perigoso. Carregar um plugin como esse pode causar erros fatais com dados de rastreamento e desabilitar um plugin pode levar a erros devido à remoção de dependência. O comando <mark style="color:yellow;">`/reload`</mark> sofre exatamente dos mesmos problemas e você pode ler mais sobre eles na postagem do [blog do me4502](https://madelinemiller.dev/blog/problem-with-reload/)

{% content-ref url="traducao-do-blog-do-me4502.md" %}
[traducao-do-blog-do-me4502.md](traducao-do-blog-do-me4502.md)
{% endcontent-ref %}


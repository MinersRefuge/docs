# Mobs

### Mobs

**configuração: tick-inactive-villagers**

`Bom valor inicial: false`

Isso permite que você controle se os aldeões devem ser marcados fora do intervalo de ativação. Isso fará com que os aldeões continuem normalmente e ignorem o intervalo de ativação. Desativar isso ajudará no desempenho, mas pode ser confuso para os jogadores em determinadas situações. Isso pode causar problemas com farm de ferro e reabastecimento comercial.

**Configuração: nerf-spawner-mobs**

`Bom valor inicial: true`

Você pode fazer com que mobs gerados por um gerador de monstros não tenham IA. Mobs nerfados não farão nada. Você pode fazê-los pular enquanto estiverem na água, alterando `spawner-nerfed-mobs-should-jump` para `true` na [configuração de mundo do Paper.](https://docs.papermc.io/paper/reference/world-configuration)

#### Arquivo: [paper-world configuration](https://docs.papermc.io/paper/reference/world-configuration)

**Configuração: despawn-ranges**

```
Bons valores iniciais:

      ambient:
        hard: 56
        soft: 30
      axolotls:
        hard: 56
        soft: 30
      creature:
        hard: 56
        soft: 30
      misc:
        hard: 56
        soft: 30
      monster:
        hard: 56
        soft: 30
      underground_water_creature:
        hard: 56
        soft: 30
      water_ambient:
        hard: 56
        soft: 30
      water_creature:
        hard: 56
        soft: 30
```

Permite ajustar os intervalos de despawn da entidade (em blocos). Abaixe esses valores para limpar os mobs que estão longe do jogador mais rapidamente. Você deve manter o alcance suave em torno de 30 e ajustar o alcance hard/bruto para um pouco mais do que a distância real da simulação, para que os mobs não desapareçam imediatamente quando o jogador for além do ponto de carregamento de uma chunk (isso funciona bem por causa do <mark style="color:yellow;">`delay-chunk-unloads-by`</mark> na [configuração por mundo do Paper](https://docs.papermc.io/paper/reference/world-configuration)). Quando um mob está fora do alcance difícil, ele desaparece instantaneamente. Quando estiver entre a faixa suave e dura, terá uma chance aleatória de desaparecer. Seu alcance forte deve ser maior do que seu alcance suave. Você deve ajustar isso de acordo com a distância de visualização usando <mark style="color:yellow;">`(simulation-distance * 16) + 8`</mark>. Isso explica parcialmente as chunks que ainda não foram descarregados depois que o jogador os visitou.

**Configuração: per-player-mob-spawns**

`Bom valor inicial: true`

Esta opção decide se os spawns de mobs devem contabilizar quantos mobs já estão ao redor do jogador alvo. Você pode contornar muitos problemas relacionados à inconsistência dos spawns de mob devido aos jogadores criarem fazendas que ocupam todo o mobcap. Isso permitirá uma experiência de desova mais parecida com a de um jogador, permitindo que você defina limites de spawn mais baixos. Habilitar isso vem com um impacto muito leve no desempenho, no entanto, seu impacto é ofuscado pelas melhorias nos limites de spawn que ele permite.

**Configuração: max-entity-collisions**

`Bom valor inicial: 2`

Substitui a opção com o mesmo nome em[ spigot.yml](https://www.spigotmc.org/wiki/spigot-configuration/). Ele permite que você decida quantas colisões uma entidade pode processar de uma só vez. O valor <mark style="color:yellow;">`0`</mark> causará incapacidade de empurrar outras entidades, incluindo jogadores. O valor de <mark style="color:yellow;">`2`</mark> deve ser suficiente na maioria dos casos. Vale a pena notar que isso tornará maxEntityCramming gamerule inútil se seu valor estiver acima do valor desta opção de configuração.

**Configuração: update-pathfinding-on-block-update**

`Bom valor inicial: false`

Desativar isso resultará em menos pathfinding sendo feito, aumentando o desempenho. Em alguns casos, isso fará com que os mobs pareçam mais lentos; Eles apenas atualizarão passivamente seu caminho a cada 5 tiques (0,25 s).

**Configuração: fix-climbing-bypassing-cramming-rule**

`Bom valor inicial: true`

Ativar isso corrigirá as entidades que não estão sendo afetadas pelo amontoamento durante a escalada. Isso evitará que quantidades absurdas de mobs sejam empilhadas em espaços pequenos mesmo que estejam escalando (aranhas).

**Configuração: armor-stands.tick**

`Bom valor inicial: false`

Na maioria dos casos, você pode definir isso com segurança como falso. Se você estiver usando suportes de armadura ou qualquer plugin que modifique seu comportamento e tiver problemas, reative-o. Isso evitará que os suportes de armadura sejam empurrados pela água ou afetados pela gravidade.

**Configuração: armor-stands.do-collision-entity-lookups**

`Bom valor inicial: false`

Aqui você pode desativar as colisões do suporte de armadura. Isso ajudará se você tiver muitos estandes de armadura e não precisar deles colidindo com nada.

**tick-rates**

```
Bons valores iniciais:

  behavior:
    villager:
      validatenearbypoi: 60
      acquirepoi: 120
  sensor:
    villager:
      secondarypoisensor: 80
      nearestbedsensor: 80
      villagerbabiessensor: 40
      playersensor: 40
      nearestlivingentitysensor: 40
```

> Não é recomendado alterar esses valores de seus padrões enquanto o DAB do Pufferfish estiver ativado!

Isso decide com que frequência os comportamentos e sensores especificados são acionados em tiques. <mark style="color:yellow;">`adquirepoi`</mark> para os aldeões parece ser o comportamento mais pesado, por isso foi bastante aumentado. Diminua-o em caso de problemas com os aldeões.

#### Arquivo: [pufferfish.yml](https://docs.pufferfish.host/setup/pufferfish-fork-configuration/)

**Configuração: dab.enabled**

`Bom valor inicial: true`

DAB (ativação dinâmica do cérebro) reduz o quanto uma entidade é processada quanto mais longe ela estiver dos jogadores. DAB funciona em um gradiente em vez de um corte brusco como EAR. Em vez de processar totalmente as entidades próximas e mal processar as entidades distantes, o DAB reduzirá a quantidade de processamento de uma entidade com base no resultado de um cálculo influenciado por <mark style="color:yellow;">`dab.activation-dist-mod`</mark>.

**Configuração: dab.max-tick-freq**

`Bom valor inicial: 20`

Define a quantidade mais lenta que as entidades mais distantes dos jogadores serão processadas. Aumentar esse valor pode melhorar o desempenho de entidades distantes da vista, mas pode quebrar farms ou nerfar muito o comportamento dos mobs. Se habilitar o DAB quebra os mob farms, tente diminuir esse valor.

**Configuração: dab.activation-dist-mod**

`Bom valor inicial: 7`

Controla o gradiente em que os mobs são processador. Diminuir isso ativará o DAB mais perto dos jogadores, melhorando os ganhos de desempenho do DAB, mas afetará como as entidades interagem com seus arredores e podem quebrar as farms de mobs. Se habilitar DAB quebra farms de mobs, tente aumentar esse valor.

**Configuração: enable-async-mob-spawning**

`Bom valor inicial: true`

Se o spawn de mob assíncrono deve ser habilitada. Para que isso funcione, a configuração <mark style="color:yellow;">`per-player-mob-spawns`</mark> do Paper deve estar habilitada. Na verdade, essa opção não gera mobs de forma assíncrona, mas descarrega muito do esforço computacional envolvido na geração de novos mobs para um thread diferente. Ativar esta opção não deve ser perceptível no jogo vanilla.

**Configuração: enable-suffocation-optimization**

`Bom valor inicial: true`

Esta opção otimiza uma verificação de sufocamento (a verificação para ver se um mob está dentro de um bloco e se deve receber dano de sufocamento), limitando a taxa de verificação ao tempo limite de dano. Essa otimização deve ser impossível de perceber, a menos que você seja um jogador extremamente técnico que está usando o tempo preciso para matar uma entidade exatamente no momento certo por sufocamento.

**Configuração: inactive-goal-selector-throttle**

`Bom valor inicial: true`

Acelera o seletor de metas de IA em tiques inativos de entidades, fazendo com que as entidades inativas atualizem seu seletor de metas a cada 20 tiques em vez de a cada tique. Pode melhorar o desempenho em alguns por cento e tem pequenas implicações na jogabilidade.

#### [purpur.yml](https://purpurmc.org/docs/Configuration/)

**Configuração: zombie.aggressive-towards-villager-when-lagging**

`Bom valor inicial: false`

Ativar isso fará com que os zumbis parem de atacar os aldeões se o servidor estiver abaixo do limite de tps definido com <mark style="color:yellow;">`lagging-threshold`</mark> em [purpur.yml](https://purpurmc.org/docs/Configuration/).

**Configuração: entities-can-use-portals**

`Bom valor inicial: false`

This option can disable portal usage of all entities besides the player. This prevents entities from loading chunks by changing worlds which is handled on the main thread. This has the side effect of entities not being able to go through portals.

**Configuração: villager.lobotomize.enabled**

`Bom valor inicial: true`

> Isso só deve ser ativado se os aldeões estiverem causando lag! Caso contrário, as verificações de pathfinding podem diminuir o desempenho.

Aldeões lobotomizados são despojados de sua IA e apenas reabastecem suas ofertas de vez em quando. Habilitar isso lobotomizará os aldeões que não conseguem encontrar o caminho para o seu destino. Libertá-los deve deslobotomizá-los.

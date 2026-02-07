# Mobs

### Arquivo: [spigot.yml](https://www.spigotmc.org/wiki/spigot-configuration/)

#### **tick-inactive-villagers**

`Bom valor inicial: false`

Isso permite que você controle se os aldeões devem ser marcados fora do intervalo de ativação. Isso fará com que os aldeões continuem normalmente e ignorem o intervalo de ativação. Desativar isso ajudará no desempenho, mas pode ser confuso para os jogadores em determinadas situações. Isso pode causar problemas com farm de ferro e reabastecimento comercial.

#### **nerf-spawner-mobs**

`Bom valor inicial: true`

Você pode fazer com que mobs gerados por um gerador de monstros não tenham IA. Mobs nerfados não farão nada. Você pode fazê-los pular enquanto estiverem na água, alterando `spawner-nerfed-mobs-should-jump` para `true` na [configuração de mundo do Paper.](https://docs.papermc.io/paper/reference/world-configuration)

### Arquivo: [paper-world configuration](https://docs.papermc.io/paper/reference/world-configuration)

#### **despawn-ranges**

Bons valores iniciais:

```yaml
      ambient:
        hard: 72
        soft: 30
      axolotls:
        hard: 72
        soft: 30
      creature:
        hard: 72
        soft: 30
      misc:
        hard: 72
        soft: 30
      monster:
        hard: 72
        soft: 30
      underground_water_creature:
        hard: 72
        soft: 30
      water_ambient:
        hard: 72
        soft: 30
      water_creature:
        hard: 72
        soft: 30
```

Permite ajustar os intervalos de despawn da entidade (em blocos). Abaixe esses valores para limpar os mobs que estão longe do jogador mais rapidamente. Você deve manter o alcance suave em torno de 30 e ajustar o alcance hard/bruto para um pouco mais do que a distância real da simulação, para que os mobs não desapareçam imediatamente quando o jogador for além do ponto de carregamento de uma chunk (isso funciona bem por causa do <mark style="color:yellow;">`delay-chunk-unloads-by`</mark> na [configuração por mundo do Paper](https://docs.papermc.io/paper/reference/world-configuration)). Quando um mob está fora do alcance difícil, ele desaparece instantaneamente. Quando estiver entre a faixa suave e dura, terá uma chance aleatória de desaparecer. Seu alcance forte deve ser maior do que seu alcance suave. Você deve ajustar isso de acordo com a distância de visualização usando <mark style="color:yellow;">`(simulation-distance * 16) + 8`</mark>. Isso explica parcialmente as chunks que ainda não foram descarregados depois que o jogador os visitou.

#### **per-player-mob-spawns**

`Bom valor inicial: true`

Esta opção decide se os spawns de mobs devem contabilizar quantos mobs já estão ao redor do jogador alvo. Você pode contornar muitos problemas relacionados à inconsistência dos spawns de mob devido aos jogadores criarem fazendas que ocupam todo o mobcap. Isso permitirá uma experiência de desova mais parecida com a de um jogador, permitindo que você defina limites de spawn mais baixos. Habilitar isso vem com um impacto muito leve no desempenho, no entanto, seu impacto é ofuscado pelas melhorias nos limites de spawn que ele permite.

#### **max-entity-collisions**

`Bom valor inicial: 2`

Substitui a opção com o mesmo nome em[ spigot.yml](https://www.spigotmc.org/wiki/spigot-configuration/). Ele permite que você decida quantas colisões uma entidade pode processar de uma só vez. O valor <mark style="color:yellow;">`0`</mark> causará incapacidade de empurrar outras entidades, incluindo jogadores. O valor de <mark style="color:yellow;">`2`</mark> deve ser suficiente na maioria dos casos. Vale a pena notar que isso tornará maxEntityCramming gamerule inútil se seu valor estiver acima do valor desta opção de configuração.

#### **update-pathfinding-on-block-update**

`Bom valor inicial: false`

Desativar isso resultará em menos pathfinding sendo feito, aumentando o desempenho. Em alguns casos, isso fará com que os mobs pareçam mais lentos; Eles apenas atualizarão passivamente seu caminho a cada 5 tiques (0,25 s).

#### **fix-climbing-bypassing-cramming-rule**

`Bom valor inicial: true`

Ativar isso corrigirá as entidades que não estão sendo afetadas pelo amontoamento durante a escalada. Isso evitará que quantidades absurdas de mobs sejam empilhadas em espaços pequenos mesmo que estejam escalando (aranhas).

#### **armor-stands.tick**

`Bom valor inicial: false`

Na maioria dos casos, você pode definir isso com segurança como falso. Se você estiver usando suportes de armadura ou qualquer plugin que modifique seu comportamento e tiver problemas, reative-o. Isso evitará que os suportes de armadura sejam empurrados pela água ou afetados pela gravidade.

#### **armor-stands.do-collision-entity-lookups**

`Bom valor inicial: false`

Aqui você pode desativar as colisões do suporte de armadura. Isso ajudará se você tiver muitos estandes de armadura e não precisar deles colidindo com nada.

#### **tick-rates**

Bons valores iniciais:

```yaml
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

Isso decide com que frequência os comportamentos e sensores especificados são acionados em tiques. <mark style="color:yellow;">`adquirepoi`</mark> para os aldeões parece ser o comportamento mais pesado, por isso foi bastante aumentado. Diminua-o em caso de problemas com os aldeões.

### Arquivo: [purpur.yml](https://purpurmc.org/docs/Configuration/)

#### **zombie.aggressive-towards-villager-when-lagging**

`Bom valor inicial: false`

Ativar isso fará com que os zumbis parem de atacar os aldeões se o servidor estiver abaixo do limite de tps definido com <mark style="color:yellow;">`lagging-threshold`</mark> em [purpur.yml](https://purpurmc.org/docs/Configuration/).

#### **entities-can-use-portals**

`Bom valor inicial: false`

Esta opção pode desabilitar o uso de portais de todas as entidades, exceto o jogador. Isso evita que as entidades carreguem chunks ao mudar de mundos, o que é processado no thread principal. Isso tem o efeito colateral de as entidades não conseguirem atravessar portais.

#### **villager.lobotomize.enabled**

`Bom valor inicial: true`

> Isso só deve ser ativado se os aldeões estiverem causando lag! Caso contrário, as verificações de pathfinding podem diminuir o desempenho.

Aldeões lobotomizados são despojados de sua IA e apenas reabastecem suas ofertas de vez em quando. Habilitar isso lobotomizará os aldeões que não conseguem encontrar o caminho para o seu destino. Libertá-los deve deslobotomizá-los.

#### **villager.search-radius**

Bons valores iniciais:

```yaml
          acquire-poi: 16
          nearest-bed-sensor: 16
```

Raio dentro do qual os villagers procurarão blocos e camas no local de trabalho. Isto aumenta significativamente o desempenho de uma grande quantidade de villagers, mas os impedirá de detectar bloqueios no local de trabalho ou camas que estejam mais distantes do que o valor definido.

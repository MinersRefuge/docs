# Entendendo o spawn

### Entendendo as mecânicas de spawn

Abaixo está um gráfico de como o spawn de mobs funciona em volta de um jogador. Os valores indicados são feitos com base no padrão Vanilla/Paper

<figure><img src="https://paper-chan.moe/content/images/2022/06/MobSpawn-Demo-Range-768x969.png" alt=""><figcaption></figcaption></figure>

<details>

<summary><strong>Explicação do gráfico:</strong></summary>

* Os cilindros marrons indicam o intervalo de geração do mob.

- A esfera vermelha indica a zona de despawn do mob (entre 24 – 128 blocos).

* A esfera amarela indica a zona livre de mob, pois nenhum mob nescerá tão perto de um jogador (24 blocos).

- Qualquer entidade que se enquadre no anel de 32 blocos (intervalo de ativação de entidade) será processada na taxa normal.

* Qualquer entidade que resida entre o anel de 32 a 128 blocos será processada a uma taxa reduzida.

- Qualquer entidade que esteja fora do 128º bloco é instantaneamente eliminada.

</details>

<details>

<summary><strong>Todo o mob no jogo vai cair em 1 das 7 categorias (Em inglês):</strong></summary>

* **monster** category consists of Piglin Brute, Blaze, Warden, Ghast, Husk, Shulker. Zoglin, Wither Skeleton, Enderman, Witch, Creeper. Zombie Villager, Vex, Elder Guardian, Evoker, Hoglin, Zombie, Piglin, Skeleton, Slime, Stray, Magma Cube, Drowned, Cave Spider, Phantom, Ender Dragon, Zombified Piglin, Ravager, Spider, Pillager. Guardian, Vindicator. Endermite, Wither, Silverfish

- **animals** or **creature** category consists of bee, cat, chicken, cow, camel, donkey, fox, goat, horse, Allay, llama, mule, mooshroom, ocelot, panda, parrot, pig, polar bear, rabbit, sheep, frog, skeleton horse, strider, trader llama, turtle, wandering trader, wolf, zombie horse.

* **ambient** category consists of bat. Bat is useless.

- **water-animals** or **water\_creature** category consists of squid and dolphins.

* **water-ambient** category consists of cod, pufferfish, salmon, tropical fish.

- **water-underground-creature** or **underground\_water\_creature** category consists of Glow Squid.

* **axolotl** category consists of Axolotl.

- **Misc** category consists of Dragon Fireball, Small Fireball, Shulker Bullet, Item Frame, Boat with Chest, Snowball, Primed TNT, Minecart with Furnace, Area Effect Cloud, Fainting, Glou Item Frame, Villager, Spectral Arrow, Lightning Bolt, Evoker Fangs, Thrown Bottle o’ Enchanting, Potion, Minecart with TNT, Llama Spit, Eye of Ender, Fishing Bobber, Arrow, Minecart with Chest, Wither Skull, Snow Golem, Thrown Egg, Minecart, Boat, Item, Marker, Player. Minecart with Hopper, Minecart with Monster Spawner, Firework Rocket, Falling Block, Fireball, Iron Golem, Thrown Ender Pearl, Armor Stand, End Crystal, Experience Orb, Leash Knot, Trident, Minecart with Command Block.

</details>

### Arquivo: [bukkit.yml](https://bukkit.fandom.com/wiki/Bukkit.yml)

#### **spawn-limits**

Bons valores iniciais:

```yaml
    monsters: 20
    animals: 5
    water-animals: 2
    water-ambient: 2
    water-underground-creature: 3
    axolotls: 3
    ambient: 1
```

A matemática para limitar mobs é `[quantiade de players] * [limite]`. Logicamente, quanto menores os números, menos mobs você verá. `per-player-mob-spawn` aplica um limite adicional a isso, garantindo que os mobs sejam igualmente distribuídos entre os jogadores. Reduzir isso é uma faca de dois gumes; sim, seu servidor tem menos trabalho a fazer, mas em alguns modos de jogo, mobs de geração natural são uma grande parte do jogo. Você pode chegar a 20 ou menos se ajustar o alcance do `mob-spawn` corretamente. Definir o `mob-spawn-range` mais baixo fará com que pareça que há mais mobs ao redor de cada jogador. Se você estiver usando o Paper, poderá definir limites de mob por mundo na [configuração por mundo do Paper](https://docs.papermc.io/paper/reference/world-configuration).

#### **ticks-per**

Bons valores iniciais:

```yaml
    monster-spawns: 10
    animal-spawns: 400
    water-spawns: 400
    water-ambient-spawns: 400
    water-underground-creature-spawns: 400
    axolotl-spawns: 400
    ambient-spawns: 400
```

Esta opção define com que frequência (em ticks) o servidor tenta gerar certas entidades vivas. Mobs de água/ambiente não precisam gerar a cada tick, pois geralmente não são mortos tão rapidamente. Quanto aos monstros: Aumentar ligeiramente o tempo entre os spawns não deve afetar as taxas de spawn, mesmo em fazendas de monstros. Na maioria dos casos, todos os valores sob esta opção devem ser maiores que `1`. Definir isso também permite que seu servidor lide melhor com áreas onde o spawn de mobs está desativada.

### Arquivo: [spigot.yml](https://www.spigotmc.org/wiki/spigot-configuration/)

#### **mob-spawn-range**

`Bom valor inicial: 3`

Permite reduzir o alcance (em chunks) de onde os mobs aparecerão ao redor do jogador. Dependendo do modo de jogo do seu servidor e sua contagem de jogadores, você pode querer reduzir este valor junto com os limites de spawn (`spawn-limits`) do [bukkit.yml](https://bukkit.fandom.com/wiki/Bukkit.yml). Definir isso mais baixo fará com que pareça que há mais mobs ao seu redor. Isso deve ser menor ou igual à sua distância de simulação e nunca maior que seu alcance de despawn / 16.

#### **entity-activation-range**

Bons valores iniciais:

```yaml
      animals: 16
      monsters: 24
      raiders: 48
      misc: 8
      water: 8
      villagers: 16
      flying-monsters: 48
```

Você pode definir a que distância do jogador uma entidade deve estar para processar (fazer coisas). Reduzir esses valores ajuda no desempenho, mas pode resultar em mobs irresponsivos até que o jogador chegue bem perto deles. Abaixar muito isso pode quebrar certas mob farms; farms de ferro sendo a vítima mais comum.

#### **entity-tracking-range**

Bons valores iniciais:

```yaml
      players: 48
      animals: 48
      monsters: 48
      misc: 32
      other: 64
```

Esta é a distância em blocos a partir da qual as entidades serão visíveis. Eles simplesmente não serão enviados aos jogadores. Se definido muito baixo, isso pode fazer com que os mobs apareçam do nada perto de um jogador. Na maioria dos casos, isso deve ser maior do que o intervalo de ativação da entidade (`entity-activation-range)`.

**Aqui está uma tabela de dicas com sugestões pré-preenchidas para a categoria de monstros:**

| Quantidade de entidades (%) | spawn-limit sugerido no bukkit.yml | Sugerido mob-spawn-range no spigot.yml | Numero calculado atual                                              |
| --------------------------- | ---------------------------------- | -------------------------------------- | ------------------------------------------------------------------- |
| 100% (Vanilla)              | 70 (Normal)                        | 8 (Normal)                             | 8 (Normal)                                                          |
| 90%                         | 63                                 | 7 ou 8                                 | 7.6                                                                 |
| 80%                         | 56                                 | 7                                      | 7.18                                                                |
| 70%                         | 49                                 | 6 ou 7                                 | 6.74                                                                |
| 60%                         | 42                                 | 6                                      | 6.26                                                                |
| 50%                         | 35                                 | 5 ou 6                                 | 5.75                                                                |
| 40%                         | 28                                 | 5                                      | 5.18                                                                |
| 30%                         | 21                                 | 4 ou 5                                 | 4.55                                                                |
| 20%                         | 14                                 | 4                                      | 3.81                                                                |
| 10%                         | 7                                  | 3                                      | 2.89                                                                |
| 3%                          | 2                                  | Por favor mude de host                 | A minha geladeira smart da Samsung consegue carregar mais entidades |

<details>

<summary>Explicação detalhada de como o cálculo é feito:</summary>

Por exemplo, se eu quiser definir meu limite de monstro para 45 e também manter a densidade de mobs aproximadamente a mesma de antes, eu resolveria a equação matemática abaixo\
\
(Limite de monstros normal) : (Área de spawn normal) = (Novo limite de monstros) : (Nova área de spawn)\
\
Onde as constantes são as seguintes,

Alcance padrão do Mob Spawn = 8 chunks \
Distância mínima onde um mob pode nascer= 24 blocos de distância de um jogador\
\
Área de spawn normal = \[ (Alcance do spawn de mob x2 x16) +1]^2 - ( 24 x2 +1 )^2 = (8x2x16+1)^2 - 49^2 = 66049 - 2401 = 63648\
\
70:63648 = 45:b; onde b = Nova Área de Spawn (em blocos)\
\
63648 x 45 = 70b

b= 40916\
\
Deixe a = Novo alance de spawn de mob, onde b = \[ (a x16 x2) +1]^2 - (24 x2 +1)^2, e b = 40916\
\
(32a +1)^2 - 2401 = 40916

(32a +1)^2 = 43317

32a +1 = 208

32a = 207

a = 6.46\
\
Eu então irei configurar o `mob-spawn-range` para `6` ou `7` no `spigot.yml`

</details>

Os números sugeridos acima são para manter a densidade de mob consistente com o Vanilla, sinta-se à vontade para criar seus próprios números que funcionem para o seu servidor. Quanto a outras categorias, nunca haverá um número ideal, pois entidades como ovelhas, vacas e peixes têm regras de desova mais complicadas e mecânicas adicionais. Por favor, leia seus próprios relatórios de tempo/faísca e faça os ajustes necessários.

<details>

<summary>Informações úteis:</summary>

* Uma farm não pode exceder o raio de (distância de simulação -1)x16 blocos.
* O valor de <mark style="color:yellow;">`hard-despawn-range`</mark> determina o ponto afk ideal da farm
* O <mark style="color:yellow;">`hard-despawn-range`</mark> deve ser sempre <mark style="color:yellow;">`igual`</mark> ao seu <mark style="color:yellow;">`(mob-spawn-range)x16`</mark> blocos e nunca menor. (Isso evita que o servidor faça um trabalho extra de gerar um mob apenas para que ele desapareça instantaneamente porque fica fora do alcance de despawn rígido)
* Utilize <mark style="color:yellow;">`/paper mobcaps`</mark> e <mark style="color:yellow;">`/paper playermobcaps`</mark> para obter detalhes adicionais sobre a geração de mob em torno de um jogador. É especialmente útil para encontrar erros no spawnproofing.
* Contanto que os mobs sejam mortos instantaneamente em uma farm, o rendimento da farm deve ser aproximadamente o mesmo do Vanilla Minecraft, dado que o design da farm é ajustado de acordo.

</details>

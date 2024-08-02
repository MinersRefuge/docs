# Chunks

### Chunks

#### Arquivo: [server.properties](https://minecraft.fandom.com/wiki/Server.properties)

**Configuração: simulation-distance**

`Bom valor inicial: 4`

A distância de simulação é a distância em chunks ao redor do jogador que o servidor processará. Essencialmente a distância do jogador que as coisas vão acontecer. Isso inclui fundição de fornalhas, plantações e cultivo de mudas, etc. Essa é uma opção que você deseja definir propositadamente para baixo, algo em torno de `3` ou `4`, devido à existência de distância de visão. Isso permite carregar mais chunks sem processá-los. Isso efetivamente permite que os jogadores vejam mais longe sem o mesmo impacto no desempenho.

**Configuração: view-distance**

`Bom valor inicial: 7`

Esta é a distância em chunks que será enviada aos jogadores, semelhante à no-tick-view-distance do Paper.

A distância total de visualização será igual ao maior valor entre a distância de simulação (`simulation-distance`) e a distância de visualização (`view-distance`). Por exemplo, se a distância de simulação for definida como 4 e a distância de visualização for 12, a distância total enviada ao cliente será de 12 blocos.

#### Arquivo: [spigot.yml](https://www.spigotmc.org/wiki/spigot-configuration/)

**Configuração: view-distance**

`bom valor inicial: default`

Esse valor sobrescreve server.properties um se não for definido como `default`. Você deve manter como padrão ter a simulação e a distância de visualização em um só lugar para facilitar o gerenciamento.

#### Arquivo: [paper-world configuration](https://docs.papermc.io/paper/reference/world-configuration)

**Configuração: delay-chunk-unloads-by**

`Bom valor inicial: 10s`

Esta opção permite que você configure por quanto tempo as chunks permanecerão carregadas depois que um jogador sair. Isso ajuda a não carregar e descarregar constantemente as mesmas chunks quando um jogador se move para frente e para trás. Valores muito altos podem resultar no carregamento de muitas chunks de uma só vez. Em áreas que são frequentemente teletransportadas e carregadas, considere manter a área permanentemente carregada. Isso será mais leve para o seu servidor do que carregar e descarregar chunks constantemente.

**Configuração: max-auto-save-chunks-per-tick**

`Bom valor inicial: 8`

Permite desacelerar o salvamento incremental do mundo distribuindo ainda mais a tarefa ao longo do tempo para um melhor desempenho médio. Você pode querer definir isso acima de 8 com mais de 20 a 30 jogadores. Se o salvamento incremental não puder terminar a tempo, o bukkit salvará automaticamente as chunks restantes de uma vez e iniciará o processo novamente.

**Configuração: prevent-moving-into-unloaded-chunks**

`Bom valor inicial: true`

Quando ativado, impede que os jogadores se movam para chunks descarregadas e causem carregamentos de sincronização que atolam o thread principal, causando lag. A probabilidade de um jogador tropeçar em uma chunks descarregada é maior quanto menor for sua distância de visão.

**entity-per-chunk-save-limit**

**Bons valores iniciais:**

```
    area_effect_cloud: 8
    arrow: 16
    breeze_wind_charge: 8
    dragon_fireball: 3
    egg: 8
    ender_pearl: 8
    experience_bottle: 3
    experience_orb: 16
    eye_of_ender: 8
    fireball: 8
    firework_rocket: 8
    llama_spit: 3
    potion: 8
    shulker_bullet: 8
    small_fireball: 8
    snowball: 8
    spectral_arrow: 16
    trident: 16
    wind_charge: 8
    wither_skull: 4
```

Com a ajuda desta configuração, você pode definir limites para quantas entidades do tipo especificado podem ser salvas por chunk. Você deve fornecer um limite pelo menos para cada projétil para evitar problemas com grandes quantidades de projéteis sendo salvos e seu servidor travando ao carregá-lo. Você pode colocar qualquer id de entidade aqui, consulte o wiki do minecraft para encontrar IDs de entidades. Por favor, ajuste o limite ao seu gosto. O valor sugerido para todos os projéteis é em torno de 10. Você também pode adicionar outras entidades por seus nomes de tipo a essa lista. Esta opção de configuração não foi projetada para impedir que os jogadores criem grandes mobs farms.

#### Arquivo: [pufferfish.yml](https://docs.pufferfish.host/setup/pufferfish-fork-configuration/)

**Configuração: max-loads-per-projectile**

`Bom valor inicial: 8`

Especifica a quantidade máxima de chunks que um projétil pode carregar durante sua vida útil. Diminuir reduzirá o peso que as chunks causarão por projéteis de entidade, mas pode causar problemas com tridentes, pérolas de ender, etc.

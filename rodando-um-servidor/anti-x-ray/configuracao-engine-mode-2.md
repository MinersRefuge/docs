# Configuração - engine-mode: 2

**Configuração pro everworld**

Substitua o bloco <mark style="color:yellow;">`anticheat.anti-xray`</mark> existente em <mark style="color:yellow;">`paper-world-defaults.yml`</mark> pelo seguinte:

```
anticheat:
  anti-xray:
    enabled: true
    engine-mode: 2
    hidden-blocks:
    # Você pode adicionar ar aqui de forma que muitos buracos sejam gerados.
    # Isso funciona bem contra localizadores de cavernas, mas pode causar quedas de FPS do cliente para todos os jogadores.
    - air
    - copper_ore
    - deepslate_copper_ore
    - raw_copper_block
    - diamond_ore
    - deepslate_diamond_ore
    - gold_ore
    - deepslate_gold_ore
    - iron_ore
    - deepslate_iron_ore
    - raw_iron_block
    - lapis_ore
    - deepslate_lapis_ore
    - redstone_ore
    - deepslate_redstone_ore
    lava-obscures: false
    # A partir de 1.18 alguns minérios são gerados muito mais alto.
    # Por favor, ajuste a configuração de altura máxima do bloco a seu critério.
    # https://minecraft.fandom.com/wiki/Ore pode ser útil.
    max-block-height: 64
    replacement-blocks:
    # O baú é uma entidade de bloco e não pode ser adicionado a hidden-blocks no engine-mode: 2.
    # Mas adicionar baú aqui esconderá tesouros enterrados, se a altura máxima do bloco for aumentada.
    - chest
    - amethyst_block
    - andesite
    - budding_amethyst
    - calcite
    - coal_ore
    - deepslate_coal_ore
    - deepslate
    - diorite
    - dirt
    - emerald_ore
    - deepslate_emerald_ore
    - granite
    - gravel
    - oak_planks
    - smooth_basalt
    - stone
    - tuff
    update-radius: 2
    use-permission: false
```

**Configuração pro nether**

Copie e cole em seu <mark style="color:yellow;">`paper-world.yml`</mark> dentro de sua pasta do nether.

```
anticheat:
  anti-xray:
    enabled: true
    engine-mode: 2
    hidden-blocks:
    - air
    - ancient_debris
    - bone_block
    - glowstone
    - magma_block
    - nether_bricks
    - nether_gold_ore
    - nether_quartz_ore
    - polished_blackstone_bricks
    lava-obscures: false
    max-block-height: 128
    replacement-blocks:
    - basalt
    - blackstone
    - gravel
    - netherrack
    - soul_sand
    - soul_soil
    update-radius: 2
    use-permission: false
```

**Configuração pro end**

Copie e cole em seu <mark style="color:yellow;">`paper-world.yml`</mark> dentro de sua pasta do end.

```
anticheat:
  anti-xray:
    enabled: false
```

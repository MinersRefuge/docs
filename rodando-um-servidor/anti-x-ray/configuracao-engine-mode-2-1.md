# Configuração - engine-mode: 3

## **Configuração pro overworld**

Substitua o bloco <mark style="color:yellow;">`anticheat.anti-xray`</mark> existente em <mark style="color:yellow;">`paper-world-defaults.yml`</mark> pelo seguinte:

```yaml
anticheat:
  anti-xray:
    enabled: true
    engine-mode: 3
    hidden-blocks:
    # You can add air here such that many holes are generated.
    # This works well against cave finders but may cause client FPS drops for all players.
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
    # As of 1.18 some ores are generated much higher.
    # Please adjust the max-block-height setting at your own discretion.
    # https://minecraft.wiki/w/Ore might be helpful.
    max-block-height: 64
    replacement-blocks:
    # Chest is a tile entity and can't be added to hidden-blocks in engine-mode: 2.
    # But adding chest here will hide buried treasures, if max-block-height is increased.
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

## **Configuração pro nether**

Copie e cole em seu <mark style="color:yellow;">`paper-world.yml`</mark> dentro de sua pasta do nether.

```yaml
anticheat:
  anti-xray:
    enabled: true
    engine-mode: 3
    hidden-blocks:
    # See note about air and possible client performance issues above.
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

## **Configuração pro end**

Copie e cole em seu <mark style="color:yellow;">`paper-world.yml`</mark> dentro de sua pasta do end.

```yaml
anticheat:
  anti-xray:
    enabled: false
```

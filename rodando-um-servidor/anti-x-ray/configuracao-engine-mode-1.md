# Configuração - engine-mode: 1

**Configuração pro overworld**

Substitua o bloco <mark style="color:yellow;">`anticheat.anti-xray`</mark> existente em <mark style="color:yellow;">`paper-world-defaults.yml`</mark> pelo seguinte:

```
anticheat:
  anti-xray:
    enabled: true
    engine-mode: 1
    hidden-blocks:
    # Não há chance de esconder baús de masmorra, pois eles são totalmente cercados por ar, mas tesouros enterrados serão escondidos.
    - chest
    - coal_ore
    - deepslate_coal_ore
    - copper_ore
    - deepslate_copper_ore
    - raw_copper_block
    - diamond_ore
    - deepslate_diamond_ore
    - emerald_ore
    - deepslate_emerald_ore
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
    # A lista de blocos de substituição não é usada no engine-mode: 1. Alterar isso não terá efeito.
    replacement-blocks: []
    update-radius: 2
    use-permission: false
```

**Configuração pro nether**

Copie e cole em seu <mark style="color:yellow;">`paper-world.yml`</mark> dentro de sua pasta do nether.

```
anticheat:
  anti-xray:
    enabled: true
    engine-mode: 1
    hidden-blocks:
    - ancient_debris
    - nether_gold_ore
    - nether_quartz_ore
    lava-obscures: false
    max-block-height: 128
    # A lista de blocos de substituição não é usada no engine-mode: 1. Alterar isso não terá efeito.
    replacement-blocks: []
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

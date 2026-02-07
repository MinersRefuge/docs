# O que está causando lag? - Medindo desempenho

## mspt

O Paper oferece o comando `/mspt` que irá te dizer quanto tempo o servidor levou para calcular os ticks recentes. Se o primeiro e o segundo valor que você vê forem menores que 50, então parabéns! Seu servidor não está com lag! Se o terceiro valor estiver acima de 50, significa que houve pelo menos 1 tick que demorou mais. Isso é completamente normal e acontece de vez em quando, então não entre em pânico.

## Spark

[Spark](https://spark.lucko.me/) é um plugin que permite analisar o uso de CPU e memória do seu servidor. Você pode ler sobre como usá-lo [na wiki dele](https://spark.lucko.me/docs/). Também há um guia sobre como encontrar a causa de picos de lag [aqui](https://spark.lucko.me/docs/guides/Finding-lag-spikes).

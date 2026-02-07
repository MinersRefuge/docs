# Pré geração de mapa

A pré-geração do mapa, graças a várias otimizações para a geração de blocos adicionadas ao longo dos anos, agora é útil apenas em servidores com CPUs que contenham um single core horrível ou extremamente limitadas. No entanto, a pré-geração é comumente usada para gerar blocos para plugins de mapa, como Pl3xMap ou Dynmap.

Se você ainda deseja pré-gerar o mundo, pode usar um plugin como o [Chunky ](https://www.spigotmc.org/resources/chunky.81534/)para fazer isso. Certifique-se de configurar uma borda para que seus jogadores não gerem novos blocos! Observe que a pré-geração às vezes pode levar horas, dependendo do raio definido no plugin de pré-geração. Lembre-se de que, com o Paper e acima, o tps não serão afetados pelo carregamento de chunks, mas a velocidade de carregamento de chunks pode diminuir significativamente quando a CPU do servidor estiver sobrecarregada.

É importante lembrar que o overword, o nether e o end têm borda separadas que precisam ser configuradas para cada mundo. O nether é 8x menor que o overword (se não for modificado com um datapack), então, se você definir o tamanho errado, seus jogadores podem acabar fora da borda do mundo!

Certifique-se de configurar uma borda do mundo vanilla (/worldborder set \[diâmetro]), pois limita certas funcionalidades, como a pesquisa para mapas do tesouro que podem causar picos de lag.

Leve em consideração que mapas pré gerados poderão utilizar uma grande quantidade de disco, você pode fazer uma estimativa usando o [Onlinemo](https://onlinemo.de/world).

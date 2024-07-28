# Flags de inicialização

### Flags de inicialização do Java

[Minecraft Vanilla e servidores de Minecraft na versão 1.20.5+ requerem Java 21 ou maior](https://docs.papermc.io/misc/java-install). A Oracle mudou seu licenciamento e não há mais um motivo convincente para obter o java deles. Fornecedores recomendados são [Adoptium](https://adoptium.net/) e [Amazon Corretto](https://aws.amazon.com/corretto/). Implementações alternativas de JVM, como OpenJ9 ou GraalVM, podem funcionar, no entanto, elas não são suportadas pelo Paper e são conhecidas por causar problemas, portanto, não são recomendadas no momento.

Seu coletor de lixo pode ser configurado para reduzir picos de lag causados ​​por grandes tarefas do coletor de lixo. Você pode encontrar flags de inicialização otimizados para servidores Minecraft [aqui](https://docs.papermc.io/paper/aikars-flags). Lembre-se de que esta recomendação não funcionará em implementações JVM alternativas. É recomendável usar o gerador de sinalizadores de inicialização [flags.sh](https://docs.papermc.io/paper/aikars-flags) para obter as flags de inicialização corretas para o seu servidor

Além disso, adicionar o sinalizador beta <mark style="color:yellow;">`--add-modules=jdk.incubator.vector`</mark> antes de <mark style="color:yellow;">`-jar`</mark> em seus sinalizadores de inicialização pode melhorar o desempenho. Este sinalizador permite que o Pufferfish use instruções SIMD em sua CPU, tornando alguns cálculos mais rápidos. Atualmente, é usado apenas para tornar a renderização de mapas in-game por plugins (como imageonmaps) possivelmente 8 vezes mais rápido.

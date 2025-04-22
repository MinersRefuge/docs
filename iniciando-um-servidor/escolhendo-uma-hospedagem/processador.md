# Processador

Oque realmente define a performance do seu servidor é o processador da hospedagem, não sendo a quantidade de núcleos, priorize a performance single-core do processador, o quanto cada núcleo individual conseguirá entregar.

Muitas hospedagens gostam de vender planos com "100% de CPU", "300%" ou "500%", isso está ditando quantos núcleos você terá naquele plano, a cada 100% indicando um núcleo, entretanto, estes são núcleos virtuais (Ou vCore), a maioria dos processadores conseguem transformar um núcleo físico em dois núcleos virtuais.

Também tenha algo em mente, GHz não define performance, existem várias alterações feitas de geração para geração de processador, otimizações e lógicas, tais como o cache, no qual lhe ajudará imensamente.

### Núcleos de eficiência

Evite hospedagens que utilizam processadores com núcleos de eficiência, a não ser que esteja dito explicitamente que eles estão desabilitados, qualquer processador Intel da série i a partir da 12 geração contém núcleos de eficiência, então tente evitá-los devido a sua baixa performance.

### Processadores de servidor

Estes sendo a linha Epyc, Xeon e Threadripper, além dos procesadores com a tecnologia "ARM", enquanto eles são feitos para servidores, não são o ideal para rodar um servidor de Minecraft, pois esses processadores focam em performance multi-core, sendo quanto conseguem entregar visando todos os núcleos, e Minecraft não cosegue utilizar muitos núcleos, se limitando muitas vezes á 2-4 núcleos.

### Foque no Single Core

O que nos resta é a série de processadores Ryzen da AMD, que isso será o que você estará buscando, no momento, deverá procurar por hospedagens que oferecem Ryzen de 5 ou 7 geração, a 3 geração ainda poderá servir para servidores mais básicos ou sem muitos players, ou enquanto está desenvolvendo o seu servidor. Processadores intel também são ótimas opções caso não caia no azar de utilizar algum núcleo de eficiência.

Caso deseja ter uma base e comparação, utilize o benchmark do [Geekbench](https://www.geekbench.com/), uma base mínima de 2000 pontos é o recomendado, os pontos são lineares, ou seja, se um processador A tem 2000 pontos e o B tem 4000 pontos, o B terá duas vezes mais performance.&#x20;

OBS: Os benchmarks do Geekbench são sintéticos e a performance não terá uma relação 1:1 em casos reais.

# Pesquisa Binária

Caso você tenha uma uma grande quantidade de plugins, e esteja com um erro específico que não sabe qual plugin esteja causando, uma pesquisa binária é a mais recomendada.

## Pesquisa binária VS linear

<figure><img src="../../.gitbook/assets/binary_linear.gif" alt=""><figcaption></figcaption></figure>

### Pesquisa Linear/Sequencial

Vai testando os plugins, um por um, em ordem, até o erro terminar.

### Pesquisa Binária

Uma pesquisa binária vai cortando os valores pela metade, repetidamente, até chegar no resultado esperado (O erro terminar). Dessa forma atingindo o resultado esperado em muito menos passos.

Remova metade dos seus plugins e veja se o problema foi resolvido. Se ele continuar, o problema ainda está na metade instalada.\
Continue fazendo isso com os plugins restantes até que chegou ao plugin problemático.

Sempre que remover uma metade, saberá se está na metade instalada ou na que acabou de remover, e continue com essa pesquisa binária sempre.

## Importante

* Sempre faça isso em um backup do seu servidor, nunca no principal, caso contrário, poderá quebrar sistemas ou algumas informações.

## Eficiência

A eficiência da pesquisa binária em comparação com a linear pode ser definida matematicamente.

A pesquisa linear pode tentar encontrar o problema na primeira interação, como na última interação.\
A binária, por outro lado lado, **sempre** conseguirá encontrar pelo log2(\<plugins>), com plugins sendo a quantidade de plugins.

Por exemplo, em 100 plugins a linear pode tanto demorar 1 tentativa, ou 100 tentativas, a binária, sempre conseguirá em 7 tentativas, pois log2(100) = 6.4.

Também pode calcular a chance da binária ser mais rápida do que a linear, considerando 100 plugins e um com erro:

(\<Chance de falhar>)^\<tentativas> = (99/100)^7 = 0.93 = 93%

Então, em 93% das tentativas a pesquisa binária será mais rápida do que a linear, o que faz just a quantidade de plugins e o log2 desta quantidade.


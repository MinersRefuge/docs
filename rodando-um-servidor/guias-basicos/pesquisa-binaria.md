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

Podemos comprar a pesquisa binária com a pesquisa linear, e para isso, [criei um um script](https://github.com/Zeptiny/PoorlyMadeBinarySearch). (Vamos nem comentar que depois descobri que o Python já tinha uma biblioteca exatamente para isso)

Esse script gera um número aleatório dentro um alcance definido, esse número será o seu plugin com erro, e testa das duas formas.

### Binária

A pesquisa binária é feita até o valor mínimo e o valor máximo do alcance ser igual ao valor do plugin com erro.

### Linear

Começa pelo primeiro e vai para o segundo valor, depois o terceiro, a mais simples.

### Resultados

Com 10.000 testes e um alcance máximo de 100, chegou ao seguinte resultado:

* Interações/passos Binários: 700.000
* Interações/passos Lineares: 5.028.085
* Eficiência da pesquisa binária: 718.30%

Basicamente, a pesquisa binária chegou a ser 7 vezes mais eficiente do que a linear.

<details>

<summary>Por que os passos binários são "Redondos" e matemática</summary>

Pensei que tudo pegou fogo quando fiz a segunda interação desse script, porém, é apenas pura matemática.

Da maneira que o script foi feito, ele vai chegando até o valor mínimo e máximo do alcance ser igual ao valor de erro, e então, o resultado irá depender da quantidade de interações multiplicado pela quantidade de divisões por 2 que o alcance máximo precisa ter para chegar a 1 ou menos, pode até ser conferido com um pequeno script:

```
alcance = 100
interacoes = 0
while alcance > 1:
    interacoes +=  1
    alcance = alcance / 2
    
    
print(interacoes)
print(alcance)
```

Nesse script definimos o alcance que iriamos colocar [no meu outro script](https://github.com/Zeptiny/PoorlyMadeBinarySearch), nesse caso usamos 100 (Que foi o no benchmark a cima) e iremos conseguir um resultado de 7 interações, e o número ficará com 0.78.

Então, apenas multiplicamos o resultado desse script, com a quantidade de interações que iriamos colocar no outro, e pronto! Já chegamos ao resultado.

E o resultado da pesquisa linear é totalmente probabilística! É possível que em todas as interações ela demore mais, ou que seja mais eficiente do que a binária, hora de usar matemática:

Considerando 100 plugins:

(\<Chance de falhar>)^\<tentativas> = (99/100)^7 = 0.93 = 93%

Como só consideramos um plugin com erro, dentro de 100, a chance de falhar fica 99/100, e precisamos de 7 interações binárias para chegar ao resultado.

Então, com essa simples conta, chegamos a conclusão que em 93% das tentativas a pesquisa binária será mais eficiente do que a linear!

No final nem precisava de um script.

Se eu errei em algo aqui, por favor me corrijam.

</details>


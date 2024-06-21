# Anti X-Ray

### Anti XRay

#### Arquivo: [paper-world configuration](https://docs.papermc.io/paper/reference/world-configuration)

**Configuração: anti-xray.enabled**

`Bom valor inicial: true`

Habilite isso para esconder minérios de players que usam X-ray. Habilitar isso realmente diminuirá o desempenho, no entanto, é muito mais eficiente do que qualquer plugin anti-xray. Na maioria dos casos, o impacto no desempenho será insignificante.

**Configuração: engine-mode**

Anti-Xray tem dois modos diferentes. <mark style="color:yellow;">`engine-mode: 1`</mark> substitui os blocos especificados (<mark style="color:yellow;">`hidden-blocks`</mark>) por outros blocos "falsos", `stone` (`deepslate` em y < 0), `netherrack` ou `end_stone` com base na dimensão. Em contraste, o <mark style="color:yellow;">`engine-mode: 2`</mark> substituirá os <mark style="color:yellow;">`hidden-blocks`</mark> e os <mark style="color:yellow;">`replacement-blocks`</mark> por <mark style="color:yellow;">`hidden-blocks`</mark> gerados aleatoriamente.\
\
As imagens a seguir mostram como cada modo ficará para um jogador usando Xray com a configuração recomendada tanto no overworld quanto no nether.

<figure><img src="../../.gitbook/assets/anti-xray-overworld-3443fb41851dc5d9082f2956268232a1.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/anti-xray-nether-05e6e894ce876f94d4463e1f491d1030.png" alt=""><figcaption></figcaption></figure>

Especialmente no lado do cliente, o <mark style="color:yellow;">`engine-mode: 1`</mark> é muito menos intensivo computacionalmente, enquanto o <mark style="color:yellow;">`engine-mode: 2`</mark> pode impedir melhor o Xray. Com o <mark style="color:yellow;">`engine-mode: 1`</mark>, apenas os minérios totalmente cobertos por blocos sólidos ficarão ocultos. Minérios expostos ao ar em cavernas ou água de um lago não serão escondidos. Com o <mark style="color:yellow;">`engine-mode: 1`</mark>, minérios falsos obstruem a visão de blocos reais. Se <mark style="color:yellow;">`air`</mark> for adicionado aos <mark style="color:yellow;">`hidden-blocks`</mark>, o <mark style="color:yellow;">`engine-mode: 2`</mark> ocultará efetivamente todos os minérios, mesmo aqueles expostos ao ar.

<mark style="color:yellow;">**BYPASS ANTI-XRAY**</mark>

**Extensão de alcance:** Embora o Anti-Xray sozinho impeça a maioria dos usuários de fazer raios-X em seu servidor, ele não é de forma alguma infalível. Por causa de como o Anti-Xray é (e tem que ser) implementado, é possível, em um servidor padrão, estender a gama de minérios reais que você pode ver em uma quantidade não insignificante. Isso pode ser mitigado por qualquer plug-in anti-fraude competente; no entanto, isso não está incluído fora da caixa.

**Reversão de sementes/seed:** Outro vetor de ataque é a natureza determinística da geração mundial do Minecraft. Se o cliente conseguir obter a seed do mundo, ele poderá saber a localização real de cada minério gerado, ignorando completamente o Anti-Xray. Isso pode ser parcialmente contornado tornando mais difícil para o cliente reverter a semente do mundo com a configuração de [`feature-seeds`](https://docs.papermc.io/paper/reference/world-configuration#feature-seeds), em conjunto com as opções de semente de estrutura em `spigot.yml`. Observe que esta não é uma solução completa e ainda pode ser possível para um cliente obter a semente mundial do servidor. Usar uma semente diferente para cada mundo também pode ser benéfico.

**Minérios expostos ao ar:** Tanto no <mark style="color:yellow;">`engine-mode: 1`</mark> quanto no <mark style="color:yellow;">`engine-mode: 2`</mark>, é possível para um cliente visualizar minérios expostos ao ar. Isso pode ser atenuado no <mark style="color:yellow;">`engine-mode: 1`</mark> adicionando <mark style="color:yellow;">`air`</mark> à lista de <mark style="color:yellow;">`hidden-blocks`</mark>. No entanto, fazer isso pode causar problemas de desempenho do cliente (quedas de FPS) para alguns jogadores.

#### **Configuração recomendada:**

{% content-ref url="configuracao-engine-mode-1.md" %}
[configuracao-engine-mode-1.md](configuracao-engine-mode-1.md)
{% endcontent-ref %}

{% content-ref url="configuracao-engine-mode-2.md" %}
[configuracao-engine-mode-2.md](configuracao-engine-mode-2.md)
{% endcontent-ref %}

# Classes do Java

Se você já recebeu algum erro em um plugin, já pode ter visto essa mensagem:

> PLUGIN has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 62.0

Este erro ocorre porque a versão do Java instalada no seu sistema não é compatível com a versão da classe do plugin, veja a tabela:

| **Java** | **Class Major Version** |
| :------: | :---------------------: |
|    22    |            66           |
|    21    |            65           |
|    20    |            64           |
|    19    |            63           |
|    18    |            62           |
|    17    |            61           |
|    16    |            60           |
|    15    |            59           |
|    14    |            58           |
|    13    |            57           |
|    12    |            56           |
|    11    |            55           |
|    10    |            54           |
|     9    |            53           |
|     8    |            52           |
|     7    |            51           |
|     6    |            50           |
|     5    |            49           |
|    1.4   |            48           |
|    1.3   |            47           |
|    1.2   |            46           |
|    1.1   |            45           |
|   1.0.2  |            45           |

### Para resolver este problema, siga as etapas:

1. Identifique a versão do plugin: A versão da classe mencionada no erro. No exemplo acima, é a versão 65.0.
2. Encontre a versão correspondente na tabela acima. Para o exemplo, a versão 65.0 corresponde ao Java 21.
3. Atualize e instale a versão do Java que corresponde à versão do arquivo de classe. Você pode baixar o Java pelo [Adoptium.net](https://adoptium.net).

# Compartilhamento de recursos

Muitas hospedagens gostam de compartilhar os recursos, sendo muito comum também a prática de "overselling" ou "overallocation", isto é, eles vendem mais do que tem.

<details>

<summary>Exemplo de overselling</summary>

Uma empresa tem 128GB de ram e 32 núcleos, e vende esses recursos para múltiplos clientes, porém, vendeu um total 256GB de ram e 64 núcleos, isso indicará um overselling de 100%, estão vendendo o dobro do que se tem.

Efetivamente os clientes dessa empresa poderiam usar apenas metade (1/2) do que comprou, e em uma de 300% poderia usar apenas um quarto (1/4).

Enquanto muitas empresas tomam cuidado para nunca atingir um uso de recursos de 100% no node, o que poderá levar ao crash da máquina e de todos os servidores, a performance do servidor estará degradada.

</details>

O quanto de overselling que uma empresa faz, o quão comum ou quais empresas fazem é incerto e não é fácil de ser comprovado.

### Evite Overselling/Overallocation

Nenhuma empresa irá dizer o quanto estará fazendo de overselling, ou se estará fazendo em si. Mas tem maneiras de evita-lo.

O painel que muitas empresas usam, ou se baseiam, é o chamado Pterodactyl, e tem como limitar para os servidores usaram apenas núcleos específicos, sendo possível então, permitir apenas X servidor utilizar Y núcleos, e sem outro servidor ter acesso, efetivamente dando núcleos dedicados.

Hospedagens então anunciam explicamente "vCore"/"Núcleo"/"Core" dedicados, assim você sempre terá total certeza que poderá usar tudo o que comprou.

**Observação:** Enquanto hospedagens que não realizam essa prática de núcleos dedicados venderão uma performance mais degradada, isso não significa que não conseguirá rodar o seu servidor, tanto que a maioria das hospedagens **não vendem núcleos dedicados**, um servidor de testes, para os amigos, ou pequena comunidade, **deve encontrar nenhum problema utlizando recursos compartilhados**, apenas em casos extremos que sua performance será gravemente afetada.

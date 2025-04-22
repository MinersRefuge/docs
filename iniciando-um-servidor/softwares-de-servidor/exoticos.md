# Exóticos

Não é uma categoria oficial, são Softwares que não encaixaram em nenhuma categoria citada anteriormente.

## Folia

Criado pela equipe do PaperMC e ainda em seus testes iniciais, é uma implementação que busca remover o bottleneck causado pelos softwares apenas conseguirem utilizar uma thread, buscando ser uma implementação multi-thread para servidores de Minecraft.

Ele não é, de qualquer modo, uma substituição para o Paper ou qualquer outro software de servidor, necessita de plugins feitos ou adaptados especialmente para funcionar com o Folia.

Folia é um software que necessita de muito hardware para funcionar, no Github relata um mínimo de 16 núcleos (Não threads), em seu primeiro teste utilizou dois Epyc 7713 (64 núcleos cada) e utilizou um processador a todo o seu potencial, e um total de 2TB de RAM.

Maiores lidas sobre esse software:

* [Github do Folia](https://github.com/PaperMC/Folia)
* [Blog da Paper Chan](https://paper-chan.moe/folia/)

## Geyser

Também disponível como plugin para Paper/Spigot, Velocity, Waterfall/BungeeCord e mod para Fabric, é uma implementação que busca trazer compatibilidade para jogadores Bedrock e Java conseguirem jogar juntos no mesmo servidor e interagirem entre si.

É muito utilizado e pronto para produção, o único desta lista.

Maiores lidas:

* [Site do GeyserMC](https://geysermc.org)

## MultiPaper

Ainda em Beta, é um software que busca trazer uma compatibilidade e funcionamento de vários servidores entre si como que fossem apenas um, essencialmente removendo as limitações dos servidores e aguentando uma grande quantidade de players para interagirem entre si.

Diferente do Folia, seriam vários servidores atuando junto, ainda é extremamente instável e não recomendado apra produção.

"Fork do Purpur 1.20.1 que permite que um administrador de servidor escale um único mundo em vários servidores. Vários servidores MultiPaper executam o mesmo mundo e usam um MultiPaper-Master para coordenar entre si e armazenar dados do servidor. Embora o MultiPaper-Master geralmente seja executado como um servidor independente, ele também pode ser executado como um plugin BungeeCord ou Velocity, que tem alguns benefícios, incluindo a capacidade de enviar jogadores para o servidor menos ocupado quando eles ingressam." - Github do MultiPaper

Maiores lidas:

* [Github do MultiPaper](https://github.com/MultiPaper/MultiPaper)


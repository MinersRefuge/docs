# Perguntas Frequentes (FAQ)

## Geral

### Quanto de RAM eu preciso para meu servidor?

Para versões acima da 1.13, o consenso geral é o **mínimo de 4GB de RAM**, com o **recomendado sendo 6GB de RAM**. Isso acontece devido ao "[The Flattening](https://minecraft.fandom.com/wiki/Java_Edition_1.13/Flattening)" e as grandes mudanças que a Mojang apresentou nas versões 1.13 e 1.14.

Para networks:
- **Proxy**: 1GB inicialmente
- **Lobbies**: 2GB sem problemas
- **Backend**: Abaixo da 1.13 pode funcionar com 4GB, acima busque por 6GB no mínimo

**Observação**: Esses valores não servirão para todos, estão aqui apenas como uma base. Recomenda-se primeiro testar com um valor baixo e ir aumentando conforme necessário.

Veja mais detalhes em [Utilização da RAM](../iniciando-um-servidor/escolhendo-uma-hospedagem/utilizacao-da-ram.md).

### Qual versão do Java eu preciso?

Depende da versão do Minecraft e dos plugins que você está usando. Veja a tabela completa em [Classes do Java](../materiais-recursos/java-classes.md).

**Resumo rápido:**
- Minecraft 1.20.5+: **Java 21 ou superior é obrigatório**
- Minecraft 1.17 - 1.20.4: Java 17 ou superior
- Minecraft 1.16.5 e anteriores: Java 8, 11 ou 16

Se você receber um erro como `class file version 65.0`, isso significa que seu plugin foi compilado com Java 21 e você precisa atualizar sua versão do Java.

### Qual software de servidor devo usar?

Para a maioria dos servidores, recomendamos **Paper** ou **Purpur**:

- **Paper**: O software mais usado e recomendado, focado em otimização e estabilidade
- **Purpur**: Fork do Paper com patches do Pufferfish, adiciona muitos recursos de jogabilidade e opções de personalização
- **Pufferfish**: Fork do Paper designado para grandes servidores, foco extremo em performance

Todos esses softwares suportam plugins do Bukkit/Spigot e sempre atualizam para a última versão do Minecraft.

Veja o guia completo em [Softwares de Servidor](../iniciando-um-servidor/softwares-de-servidor/README.md).

### Meu servidor está com lag, o que fazer?

1. **Identifique a causa**: Use o [Guia de Medindo Desempenho](../rodando-um-servidor/guia-de-otimizacao/medindo-desempenho.md) com o plugin Spark
2. **Siga o guia de otimização**: Veja o [Guia de Otimização](../rodando-um-servidor/guia-de-otimizacao/README.md) completo
3. **Verifique seus plugins**: Plugins mal otimizados podem causar lag severo. Pode fazer o uso de [Pesquisa Binária](../rodando-um-servidor/guias-basicos/pesquisa-binaria.md)

Comece sempre identificando o problema antes de fazer alterações aleatórias. Todas as alterações no guia de otimização trarão consequências ao seu servidor.

## Plugins e Mods

### Posso usar plugins e mods juntos?

Sim, mas você precisa de um software híbrido. As opções incluem:

- **Arclight** (Forge + Bukkit)
- **Mohist** (Forge + Bukkit)
- **Sponge** (Forge + SpongePlugins)

**Atenção**: Softwares híbridos podem ter problemas de compatibilidade e bugs. Teste bem antes de usar em produção.

Veja mais em [Híbridos](../iniciando-um-servidor/softwares-de-servidor/hibridos.md).

### Posso usar o comando `/reload`?

**NÃO.** Nunca use o comando `/reload` em nenhuma circunstância.

O comando `/reload` causa instabilidades significativas no Minecraft, Bukkit, Spigot, Paper e quase todos os plugins. Ao contrário dos primeiros dias, os plugins não podem mais oferecer suporte adequado ao comando reload.

**O que fazer em vez disso:**
- Para **adicionar/atualizar/remover plugins**: Sempre reinicie o servidor
- Para **alterar configurações**: Use o comando específico do plugin (ex: `/cb reload` para CraftBook)

Leia o artigo completo: [Tradução do blog do me4502](../rodando-um-servidor/guia-de-otimizacao/plugins/traducao-do-blog-do-me4502.md).

### Onde posso baixar plugins confiáveis?

**Fontes oficiais:**
- [SpigotMC](https://www.spigotmc.org/resources/)
- [Hangar (Paper)](https://hangar.papermc.io/)
- [Modrinth](https://modrinth.com/plugins)
- [Bukkit/CurseForge](https://dev.bukkit.org/bukkit-plugins)

**Nunca baixe:**
- Plugins de sites não confiáveis
- Versões crackeadas/leaked de plugins premium
- Plugins de fontes desconhecidas sem verificação

## Jogadores Piratas

### Posso permitir jogadores piratas no meu servidor?

Tecnicamente sim, mas **há consequências sérias**:

**Você perderá:**
- Autenticação de nicks (qualquer pessoa pode entrar com qualquer nick)
- Skins funcionais (todos aparecerão como Steve/Alex)
- Todos os dados dos jogadores existentes (itens, XP, conquistas)
- Suporte de muitos plugins e desenvolvedores
- Suporte de muitas hospedagens (pode violar o ToS)

**Se ainda quiser permitir:**
1. Instale um plugin de autenticação como **AuthMe**, **nLogin** ou **LibreLogin**
2. Altere `online-mode=false` no `server.properties`
3. Reinicie o servidor

Veja o guia completo: [Permitindo jogadores piratas](../rodando-um-servidor/guias-basicos/permitindo-jogadores-piratas.md).

## Segurança

### Como proteger meu servidor contra exploits?

1. **Mantenha tudo atualizado**: Sempre use as versões mais recentes do software do servidor e plugins
2. **Configure proteções básicas**: Veja o [Guia de Exploits](../rodando-um-servidor/exploits/exploits.md)
3. **Use whitelist**: Se o servidor for privado/semi-privado
4. **Nunca dê OP**: Use plugins de permissões como LuckPerms
5. **Configure Anti X-Ray**: Veja o [Guia de Anti X-Ray](../rodando-um-servidor/anti-x-ray/README.md)

### O que é Anti X-Ray e preciso configurar?

Anti X-Ray é uma funcionalidade do Paper que previne que jogadores usem mods de X-Ray para ver minérios através de blocos.

**Existem 3 modos:**
- **Engine Mode 1**: Substitui blocos ocultos por pedra
- **Engine Mode 2**: Mistura blocos falsos com reais
- **Engine Mode 3**: Similar ao 2, porém mais otimizado

Recomenda-se configurar pelo menos o Engine Mode 1 para servidores survival.

Veja o guia completo: [Anti X-Ray](../rodando-um-servidor/anti-x-ray/README.md).

## Hospedagem

### Posso hospedar um servidor em casa?

Sim! Veja os guias:
- [Windows](../iniciando-um-servidor/em-casa/windows.md)
- [Deixando o servidor público com Playit.gg](../iniciando-um-servidor/em-casa/deixando-o-servidor-publico/playit.gg.md)

**Considerações:**
- Verifique sua velocidade de upload e estabilidade da internet
- Considere o custo de eletricidade
- Seu IP pode ser exposto (use serviços como Playit.gg)
- Servidor ficará offline quando o PC desligar

## Domínio

### Preciso de um domínio para meu servidor?

Não é obrigatório, mas torna o acesso muito mais fácil para os jogadores.

**Sem domínio:**
- Jogadores entram com: `192.168.0.1:25565`

**Com domínio:**
- Jogadores entram com: `meuservidor.com`

Veja como configurar:
- [Constituição do domínio](../rodando-um-servidor/dominio/constituicao-do-dominio.md)
- [Contratando um domínio](../rodando-um-servidor/dominio/contratando-um-dominio.md)
- [Configurando no servidor](../rodando-um-servidor/dominio/configurando-no-servidor/README.md)

## Otimização

### O que são "Flags de inicialização" e preciso delas?

Flags de inicialização são parâmetros que você passa para a JVM (Java Virtual Machine) ao iniciar o servidor. Elas podem melhorar significativamente o desempenho.

As flags recomendadas (Aikar's flags) ajudam o Garbage Collector a funcionar melhor, reduzindo lag spikes.

Veja o guia: [Flags de inicialização](../rodando-um-servidor/guia-de-otimizacao/flags-de-inicializacao.md).

### Devo pré-gerar meu mundo?

**Sim, altamente recomendado!**

Pré-gerar o mundo elimina lag causado pela geração de chunks durante o jogo. Isso é especialmente importante para:
- Servidores com muitos jogadores
- Servidores com mundo limitado (border)
- Melhor experiência de jogo

Veja como: [Pré geração de mapa](../rodando-um-servidor/guia-de-otimizacao/pre-geracao-de-mapa.md).

### Por que a RAM do meu servidor sempre está "cheia"?

Isso é **normal e esperado**!

A JVM (Java Virtual Machine) não retorna memória não utilizada ao sistema operacional. Ela vai subir continuamente até atingir o limite máximo (flag `-Xmx`). 

Nem toda RAM mostrada como "usada" está realmente sendo usada - grande parte fica parada esperando que o servidor a utilize. O Garbage Collector limpa a RAM periodicamente quando necessário.

Leia mais: [Utilização da RAM - Garbage Collector](../iniciando-um-servidor/escolhendo-uma-hospedagem/utilizacao-da-ram.md#garbage-collector).

## Outros

### Como contribuir com esta documentação?

A documentação está sempre em desenvolvimento! 

Para contribuir:
1. Acesse o [repositório no GitHub](https://github.com/MinersRefuge/docs)
2. Faça um fork do repositório
3. Faça suas alterações
4. Abra um Pull Request

Todas as contribuições são bem-vindas!
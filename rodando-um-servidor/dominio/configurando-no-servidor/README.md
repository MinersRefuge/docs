# Configurando no servidor

Após ter contratado o seu domínio vai certamente querer usar ele no seu servidor agora. Cada empresa tem um painel diferente, mas a lógica é a mesma para todas.

Para prosseguir, terá que ter em mente as seguintes coisas:

* Se irá usar o seu domínio (seuservidor.com) ou subdomínio (jogar.seuservidor.com)
* Qual o IP númerico do seu servidor
* Quais portas o seu servidor está utilizando
* Ter acesso total para alterar os registros DNS do seu domínio

É importante notar que para melhor configuração e menos problemas, o IP do seu servidor deverá ser estático, isso é, não mudar com o tempo ou após reinicializações da máquina.\
É padrão todas as hospedagens entregarem IPs estáticos, porém, em outros casos (Como hospedando em casa), o IP poderá ser dinâmico e causar problemas.\
Caso o seu IP seja dinâmico, precisará utilizar algo como DDNS (Dynamic DNS), para atualizar o DNS automaticamente sempre que o IP atuailizar, essa configuração de DDNS não está coberta na documentação no momento.

## Tutoriais

Caso a sua não esteje listada, poderá seguir a lógica, os paineis normalmente são extremamente parecidos.

{% content-ref url="cloudflare/" %}
[cloudflare](cloudflare/)
{% endcontent-ref %}

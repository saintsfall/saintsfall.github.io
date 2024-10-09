---
{"dg-publish":true,"permalink":"/docs-cs-es/src/site/notes/02-processos/cs-ajuda/migracao-de-liquid/","tags":["gardenEntry"]}
---



## Migração de liquid

A acordada a alteração com o seller a partir do seguinte texto:

## TEXTO PARA O SELLER  

Verificamos por aqui que a sua loja possuí o modelo antigo de código implementado no momento do desenvolvimento, sendo o liquid2.

O recomendado pela equipe de front-end seria a atualização do liquid (versão do código) da loja para o mais recente, o liquid4, antes da realização dos novos pontos de implementação desejados.

Explicando um pouco sobre o sistema Liquid: Ele é utilizado na Vnda como base no código para a criação dos sites, existem duas versões dele: Liquid2 (versão das lojas mais antigas da Vnda/versão inicial) e o Liquid4 (versão das lojas mais recentes/versão atual).  
De acordo com a versão de liquid de cada loja, os ajustes e implementações são feitos de formas diferentes. Algumas alterações possíveis de serem realizadas em lojas que possuem a versão do liquid4, não são possíveis de serem feitas no liquid2, ou implementações de features mais atuais em lojas que possuem o código muito antigo, como este caso.

A atualização de liquid se trata de uma atualização no código, para que o mesmo fique com a base interna mais recente e para que os tratamentos no código sejam mais efetivos e simples para nossos desenvolvedores.

As features de layout não sofrem alterações. A migração se dá somente para os pontos supracitados, e para que o time de front possa ter um código mais limpo e atual para mexer.

Em questões visuais do site, nada sofrerá alterações.

Ela também não possuí custos para realização.
A migração é realizada primeiro em ambiente de testes e leva cerca de 15 à 20 dias úteis após a aprovação da data de iniciação.
Após ser realizada, avisamos o cliente e marcamos o melhor dia para a virada do liquid, com no mínimo dois dias de antecedência. Assim, por poderem ocorrer pequenos bugs no site na hora da atualização, acompanhamos a loja durante o dia validando se há algum erro ocorrendo.

O ideal é realizarmos a migração antes de termos a confirmação do orçamento, pois com o cenário atual do código é quase inviável de realização, pode levar um longo tempo de desenvolvimento e ter um custo superior pela dificuldade.  

Assim, orçamos após esta atualização do código, e a LOJA já irá possuir um código limpo e atualizado para todas as próximas atualizações. Isso também assegura a loja a possuir um código mais recente, evitando certos bugs que podem ocorrer.

***

Para o processo de migração do liquid da loja da versão 2 para a versão 4 precisamos seguir o seguinte fluxo:

## IMPORTANTE

*A loja no processo de migração NÃO TERÁ DESENVOLVIMENTOS OU CORREÇÕES.
Tanto a versão de STG quanto a de PROD tem suas versões controladas individualmente, ou seja, STG e PROD podem ter versões de liquid diferentes.
Nesses casos NÃO É POSSIVEL efetuar o deploy de um código liquid 2 em uma loja liquid 4 ou vice-versa.*

*Dessa maneira durante o processo de migração o seller precisa estar ciente de que não podemos fazer nenhum desenvolvimento, correção ou implementação.*

### Abertura do card
- O card precisa conter todas as informações relevantes sobre o negócio do seller, assim como os cenários de venda diferenciados, para que a equipe de frontend possa fazer uma melhor analise do código
- Componentes utilizados nas lojas mais atuais poderão ser instalados na migração como: Cart Drawer, Newsletter... etc

### Abertura do ticket para apontamento dos assets (STG) 
- É efetuado a abertura de um ticket em feature base https://productvnda.featurebase.app/pt solicitando o apontamento dos assets da loja para versão s3 em STG
- A abertura do ticket é feita pela equipe de frontend

### Review da migração
- Após o desenvolvimento por parte da equipe de frontend todos os processos e fluxos da loja precisam ser revisados garantindo que a migração do código não ocasionou em nenhum problema na loja.


### Abertura do ticket para apontamento dos assets (PROD) 
- Antes de fazer o processo de deploy do código atualizado para produção é necessário também solicitar via ticket no feature base o apontamento dos assets da loja para versão s3 em PROD
- **IMPORTANTE** Esse processo precisa ser solicitado com antecedência para o pessoal de N2 visando não impactar as vendas do seller em produção

### Deploy do código atualizado
- Depois de efetuados os apontamentos o pessoal de frontend faz o deploy do código para produção para que o mesmo ambiente funcional em STG seja replicado para o cenário atual de PROD
---
{"dg-publish":true,"permalink":"/08-referencias/referencia-trustvox/","tags":["helpers"],"noteIcon":"","created":"2024-10-09T16:52:26.954-03:00","updated":"2024-10-10T09:42:33.979-03:00"}
---

Para implementar trustvox é necessário ter acesso ao painel do seller no site da ferramenta. Tendo isso, é necessário identificar o ID da loja e o Token que será utilizado no admin. Nesta documentação de opiniões em carrossel já é detalhado como conseguir isso: https://help.trustvox.com.br/pt-BR/articles/5557670-como-adicionar-as-opinioes-de-loja-carrossel-da-ra-trustvox-em-seu-site

Na plataforma do admin é preciso selecionar a integração de Trustvox nas configurações e adicionar o token e a url de endpoint de pedidos, como explicado nesta documentação: https://help.trustvox.com.br/pt-BR/articles/5560981-integracao-via-api-da-ra-trustvox. Na url referenciada precisa ser subsituído o store_id pelo ID da loja que foi informado no painel da própria Trustvox. Exemplo: https://trustvox.com.br/api/stores/111111/orders.

No admin da VNDA:

![trustvox_admin_1.png](/img/user/01_Assets/trustvox_admin_1.png)

![trustvox_admin_2.png](/img/user/01_Assets/trustvox_admin_2.png)

##### Documentação Trustvox de implementação de opiniões em carrossel: 
https://help.trustvox.com.br/pt-BR/articles/5557670-como-adicionar-as-opinioes-de-loja-carrossel-da-ra-trustvox-em-seu-site

##### Documentação Trustvox de implementação de opiniões de produto: 
https://help.trustvox.com.br/pt-BR/articles/5557705-como-exibir-as-opinioes-e-adicionar-os-scripts-da-ra-reviews-de-forma-generica


###### Em Yuool os scripts de trustvox estão sendo adicionados por javascript, segue os links do gitlab das funções:

- **Carrossel de opiniões da home:** https://gitlab.com/vnda/setup/yuool2/-/blob/master/assets/javascripts/store.js?ref_type=heads#L1536

- **Reviews de produto:** https://gitlab.com/vnda/setup/yuool2/-/blob/master/assets/javascripts/store.js?ref_type=heads#L1574

- **Estrelas de review:** https://gitlab.com/vnda/setup/yuool2/-/blob/master/assets/javascripts/store.js?ref_type=heads#L1555

- **OBS: Estas utilizam uma função que verifica se os elementos estão no viewport -** https://gitlab.com/vnda/setup/yuool2/-/blob/master/assets/javascripts/store.js?ref_type=heads#L1524

Caso necessário, dar uma analisada na implementação geral da loja pode ajudar: https://gitlab.com/vnda/setup/yuool2



---
{"dg-publish":true,"permalink":"/02-processos/search-console/","tags":["docs"],"noteIcon":"","created":"2024-10-09T16:52:26.949-03:00","updated":"2024-10-10T09:41:44.230-03:00"}
---


## Mensagens de erros e avisos no Search Console

No Google Search Console na sessão de Páginas podemos ver que alguns itens são retornados nas métricas conforme imagem abaixo:

![search_console_1.png](/img/user/01_Assets/search_console_1.png)
Dentro desses itens exibidos existem algumas tratativas a serem efetuadas quando:

 

### Não encontrado (404)

Nesses casos se tratam de prováveis páginas de produtos que não estão mais disponíveis, desativados ou que tiveram seu nome alterado.

Para estes itens a tratativa deve ser de criar o redirecionamento para estes itens.

A relação das URLs pode ser exportada dentro do Search Console conforme abaixo:

![search_console_2.png](/img/user/01_Assets/search_console_2.png)

Após exportadas as URLs elas deve ter a tratativa de redirecionamento e podem ser inseridas dentro do admin.

*IMPORTANTE:* 
*O item de redirecionamento de URL só fica disponível no admin da loja em Produção*

![search_console_3.png](/img/user/01_Assets/search_console_3.png)

Dentro desse item é possível efetuar o upload do arquivo com os redirecionamentos.

*** 
### Erro soft 404

Este item não há tratativa, eles vão acontecer por conta de como funcionam as tags na plataforma.

Não temos como atuar nesses itens.

***


### Bloqueada devido a acesso proibido (403)

Esse item necessita de uma analise, muitas vezes os itens estão relacionados a páginas de alguma plataforma de eCommerce anterior que a loja possa ter utilizado.

Exemplo:

![search_console_4.png](/img/user/01_Assets/search_console_4.png)

Nesse item temos diversas URLs que são de um tipo de busca que que não é utilizada pela plataforma.

`/busca.php?`

Este itens podem ser adicionadas na remoção de páginas adicionando páginas que tenham esse prefixo `/busca.php`


Outros itens precisam ser analisados para que sejam possível verificar se temos alguma tratativa possivel.

***

### Sitemaps

O site maps é gerado automaticamente por uma rotina feita em backend. 
Os dados que são gerados, conteúdo das tags, correções etc... não são gerados pelo frontend.
No admin pode ser informado o caminho para o arquivo que normalmente é `https://url_da_loja.com.br/sitemaps.xml` e feitas edições no arquivo também.

![sitemap_1.png](/img/user/01_Assets/sitemap_1.png)

![sitemap_2.png](/img/user/01_Assets/sitemap_2.png)

![sitemap_3.png](/img/user/01_Assets/sitemap_3.png)

Caso o item apontado não esteja disponível na edição do sitemap no admin é necessário utilizar o próprio app da vnda no link https://sitemap.vnda.com.br/
Porém esse app precisa de acesso para ser acessado.

***
### Tag canonical

Problemas com a tag canonical, onde o item está vindo com parâmetros ou está vindo com outros itens.

Podemos fazer uma alteração via script no código para corrigir o problema com o script abaixo:

```javascript
// =================================================
// Atualiza o a Tag Canônica - Remoçaõ de parâmetros
// =================================================
export function updateCanonicalTag() {
  const canonicalLink = document.querySelector('link[rel="canonical"]');

  if (canonicalLink) {
    let canonicalURL = canonicalLink.getAttribute('href');

    // Verifica se a URL canônica contém algum parâmetro
    if (canonicalURL.includes('?')) {
      // Guarda apenas o conteúdo sem parâmetros
      canonicalURL = canonicalURL.split('?')[0];

      // Atualiza a tag canônica com o link sem parâmetros
      canonicalLink.setAttribute('href', canonicalURL);
    }
  }
}
```



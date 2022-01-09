## O que é ?
E uma forma de buscar um dado de um servidor ou computador que ao invés de buscar o dado novamente no servidor, esse dado fica salvo

## Tipos de cache que podemos usar
### Arquivos temporários da internet
- São arquivos que não são modificados com frequencia e ficam salvos no nosso browser, evitando com que toda a requisição busque aquele dado em todas as requisições(Imagens são ótimos exemplos)

### Servidor Proxy (N é muito utilizado atualmente)
- É um sistema que fica no meio da requisição entre o servidor e o cliente e serve como um cache compartilhado entre os clientes que tentam acessar o servidor, no entanto, n consegue fazer cache de recuursos criptografados (HTTPS)

### CDN( Content Delivery Network)
- Consiste em empresas grandes com sevidores de cache  armazenam arquivos estátivos, como a cloudflare e Amazon cloudFront, onde os arquivos estáticos ficam salvos e entregam para alguns clientes esses dados, ao invés de fazer a requisição novamente para o servidor
    

### Glossário
TTL-> Time to live ou tempo de vida do cache


### DONE
- Criar um CDN com uma aplicacao para evitar bater no servidor 

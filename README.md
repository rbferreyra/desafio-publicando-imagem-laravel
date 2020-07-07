# Publicando imagem Laravel

## Instruções

1. Configurar um ambiente Laravel utilizando o docker-compose com:

* Nginx
* PHP-FPM
* Redis
* MySQL

Lembrando que o volume do código fonte deve ser compartilhado com a App.

Após realizarmos a clonagem do repositório e executarmos: docker-compose up -d, poderemos ver a aplicação Laravel rodando com o erro de autoload na porta: 8000, uma vez que o docker-compose não executou o composer install do PHP, logo, não se preocupe com tal detalhe nesse momento.

2. Após ter tido sucesso na etapa anterior, faça a configuração do framework Laravel seguindo as etapas (dentro do container):

execute composer install
crie o arquivo .env baseado no .env.example
execute: php artisan key:generate
execute: php artisan migrate

Nesse momento, quando você acessar a aplicação no browser, finalmente, você deverá ver a página inicial do Laravel funcionando.

Baseado nessas últimas ações, gere o build da imagem desse container e faça a publicação em sua conta no Hub do Docker.

Lembre-se: Ao gerar o build da imagem, TODO o conteúdo incluindo arquivos como vendor, .env, etc deverão ser incluídos.

Adicione o endereço da imagem do seu dockerhub no README.md e faça o commit do projeto contendo todos os arquivos (laravel + docker) para um repositório público do Github.


## Docker

Criar tag do projeto para o repositório

```bash
docker tag laravel_app rbferreyra/desafio-publicando-imagem-laravel
```

Publicar imagem para o repositório

```bash
docker push rbferreyra/desafio-publicando-imagem-laravel 
```

Repositório da imagem

https://hub.docker.com/repository/docker/rbferreyra/desafio-publicando-imagem-laravel

## Aplicação

Clonar o repositório e executar os comandos abaixo:

```bash
composer install
```

Executar a migration da aplicação

```bash
php artisan migrate
```

Rodar a aplicação

http://localhost:8000

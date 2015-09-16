# Easychat for Laravel 4 & 5

## Descrição

Chat baseado em jQuery para Laravel 4 & 5 utilizando armazenamento em banco de dados MySQL e integração com a tabela de usuários do seu projeto.

## Instalação

Para instalar o Easychat, você deve adicionar a linha abaixo no fim da lista de `providers`, do arquivo `app.php` do seu projeto:

`'Ronanflavio\Easychat\EasychatServiceProvider',`

Em seguida você deve entrar com o seguinte comando via composer:

`composer require "ronanflavio/easychat"`

É necessário publicar os assets e configurações do package em seu projeto, para isso execute o comando abaixo:

`php artisan asset:publish`

Existem tabelas que são necessárias para o funcionamento do chat, elas estão nomeadas com o prefixo `ec_`, com o intuito de diferenciá-las das tabelas do seu projeto. As migrations dessas tabelas estão dentro do package, para executá-las, utilize o comando abaixo:

`php artisan migrate --package=ronanflavio/easychat`

## Configuração

Quando fizer a publicação do package, os arquivos de configuração estarão dentro do diretório:

`app\config\packages\ronanflavio\easychat`

É necessário informar qual o nome da tabela, da model e dos campos respectivos à tabela de usuários dentro do arquivo `tables.php`. Veja abaixo o exemplo:

```
'users' => array(

        /**
         * Set the Model name:
         */

        'model' => 'Usuario',

        /**
         * Set the Table name:
         */

        'table' => 'usuarios',

        /**
         * Set the Fields names:
         */

        'id'         => 'id',
        'name'       => 'nome',
        'photo'      => null,
        'created_at' => 'created_at',
        'updated_at' => 'updated_at',
    ),
```

É necessário também que exista um campo com o nome do usuário dentro da sua tabela de usuários, como vemos no exemplo acima.
Caso na sua tabela de usuários existe um campo com o diretório para a imagem de exibição do usuário, você deve atribuir o nome desse campo na chave `photo` do array. Deixando o valor como `null`, o sistema irá utilizar uma imagem padrão.

-------------------------------------

## Description

jQuery based chat for Laravel 4 &amp; 5 with database storage and integration with your users table.

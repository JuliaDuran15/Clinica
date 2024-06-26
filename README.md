# Site TECH.com

## Passo a passo
Clone repositório criado a partir do template, entre na pasta e execute os comandos abaixo:
### Entre no arquivo:
```sh
cd Projetao
```

Crie o Arquivo .env
```sh
cp .env.example .env
```


Atualize as variáveis de ambiente do arquivo .env
```dosini
APP_NAME=Laravel
APP_URL=http://localhost:8080

DB_PASSWORD=root
```


Suba os containers do projeto
```sh
docker compose up -d
```


Acessar o container
```sh
docker compose exec app bash
```


Instalar as dependências do projeto
```sh
composer install
```


Gerar a key do projeto Laravel
```sh
php artisan key:generate
```


Subir as tabelas da apliacação
```sh
php artisan migrate
```


Instalar pacote UI no Laravel
```sh
composer require laravel/ui
```

Instalar pacote Breeze no Laravel
```sh
composer require laravel/breeze
```
```sh
php artisan breeze:install api
```
```sh
php artisan migrate
```
Fora do terminal do laravel 
```sh
npm install
```


### Entre no vite-project (em outro terminal)
```sh
cd vide-project
```
Instale necessarios
```sh
npm install
```
```sh
npm install express vue vue-router@4
```
```sh
npm install pinia axios
```
```sh
npm run dev
```

### Na pasta principal:
```sh
npm install
```
```sh
npm install electron
```
```sh
. electron
```

Acesse o projeto
[http://localhost:8080](http://localhost:8080)

Acesse o phpmyadmin
[http://localhost:8081](http://localhost:8081)

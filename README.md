## Instalação
Esse sistema segue a estrutura de modulos, para usá-lo você precisará instalar o gerenciador de modulos do laravel ``laravel-modules``

## laravel-modules
``` bash
composer require nwidart/laravel-modules
``` 

### Autoloading

Para carregar o autoload edite esse trecho no composer.json:

``` json
{
	"autoload": {
	"psr-4": {
		"App\\": "app/",
		"Database\\Factories\\": "database/factories/",
		"Database\\Seeders\\": "database/seeders/",
		"Modules\\": "Modules/"
	}
}
```

***Não se esqueça de executar o comando de dump do autoload `composer dump-autoload`.***

### Descompacte o modulo
Agora descompacte os arquivos do modulo:
Em servidore linux:  `unzip ´ggames-[nome_jogo].zip`

### Migration
A seguir, execute o migration
``` bash
php artisan module:migrate GGdSSubwaySurfers

```

### Finalizanção
Devido a variação de cada plataforma você deve registrar o jogo manualmente na sua lista de jogos, lembrando que o grupo de rotas a seguir será reservada para o jogo:
``
ggames/[nome_jogo]
``
Tudo abaixo dessa rota estará reservado para o jogo em questão.
#### CSRF
Adicione a rota `ggames/*` nas excessões do csrf em `app/Http/Middleware/VerifyCsrfToken.php`

### Jogar Subway Surfer:
``/ggames/subwaysurfers/play?api_exit=/``

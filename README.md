# Pacote de Busca de Cursos Alura

Pacote desenvolvido durante o curso de Composer da Alura. Este projeto utiliza as bibliotecas Client HTTP e DOM Crawler para acessar o site da Alura e buscar informações sobre cursos.

## Funcionalidades

- Acessa o site da Alura
- Faz buscas por cursos
- Exibe os resultados encontrados na tela

## Tecnologias Utilizadas

- <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/php/php-original.svg" width="14" height="14"/> PHP
- <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/composer/composer-original.svg" width="14" height="14"/> Composer
- <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/guzzle/guzzle-original.svg" width="14" height="14"/> GuzzleHttp
- <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/symfony/symfony-original.svg" width="14" height="14"/> Symfony DomCrawler

## Instalação

1. Certifique-se de ter o PHP e Composer instalados
2. Clone este repositório
3. Execute `composer require oliveira-fp/buscador-cursos` para instalar as dependências

## Como usar

```php
// Exemplo de uso
<?php

require 'vendor/autoload.php';

require 'src/Buscador.php';

use Alura\BuscadorDeCurso\Buscador;
use GuzzleHttp\Client;
use Symfony\Component\DomCrawler\Crawler;

$client = new Client(['base_uri' => 'https://www.alura.com.br/']);
$crawler = new Crawler();

$buscador = new Buscador($client,$crawler);
$cursos = $buscador->buscar('/cursos-online-programacao/php');

foreach ($cursos as $curso) {
    echo $curso . PHP_EOL;
}

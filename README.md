# Docker - PHP

![Docker Pulls](https://img.shields.io/docker/pulls/mestre8d/docker-php.svg)
![Docker Automated](https://img.shields.io/docker/cloud/automated/mestre8d/docker-php.svg)
![Docker Build](https://img.shields.io/docker/cloud/build/mestre8d/docker-php.svg)

Esse repositório armazena o código-fonte do arquivo de construção das imagens do PHP-FPM.

* [Caracteristicas](#caracteristicas)
  * [PHP](#imagem-base)
* [Dockerfiles](#tags-e-dockerfiles)

## Caracteristicas

### Imagem base

A imagem base conta com:

* O ID/GID do usuario www-data foi definido como 1000:1000;
* O arquivo php.ini esta configurado para ambientes de desenvolvimento;
* [Composer](http://getcomposer.org/http://getcomposer.org/) globalmente instalado;
* Os seguintes pacotes de sistema:  
  * Alpine:
    * shadow 
    * libpng-dev
    * jpeg-dev
    * libxml2-dev
    * libxslt-dev
    * libzip-dev
    * freetype-dev
    * postgresql-dev 
    * libxml2-dev
    * zlib-dev
    * icu-dev
    * gettext-dev
    
* Os seguintes pacotes PHP:
  * bcmath (Somente Debian)
  * bz2 (Somente Debian)
  * dom
  * gd (com suporte a PNG, JPG e TrueType)
  * gettext
  * hash
  * intl
  * json
  * mbstring
  * mysqli
  * pdo 
  * pdo_mysql
  * pdo_pgsql 
  * pgsql 
  * phar
  * posix 
  * simplexml 
  * soap 
  * xml 
  * xmlrpc
  * xmlwriter 
  * zip
  * xmlreader
  * imagick
  * mcrypt

## Tags e Dockerfiles

* 7.4
  * [7.4-fpm-alpine](7.4/fpm/alpine/Dockerfile)



  

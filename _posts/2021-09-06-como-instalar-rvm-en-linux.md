---
title: Cómo instalar RVM en Linux
date: 2021-09-06 20:00:00 -0500
categories: [tutoriales]
tags: [linux, ruby]
---

RVM es una herramienta de linea de comando, que permite fácilmente instalar, manejar y trabajar con múltiples entornos de Ruby. Para instalarlo en tu distribución GNU/Linux sigue los siguientes pasos:

## Instala las llaves GPG

Para la verificación de los paquetes sera necesario la instalación de las siguientes llaves:

`gpg --keyserver hkp://pgp.mit.edu --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB`

## Instala RVM con Ruby

El siguiente comando instala la versión estable de RVM junto a la ultima versión de Ruby.

`\curl -sSL https://get.rvm.io | bash -s stable --ruby`

### Configura la instalación

Remplaza en el siguiente comando `usuario` por tu nombre de usuario y ejecutalo.

`source /home/usuario/.rvm/scripts/rvm`

## Instala una versión diferente de Ruby

`rvm install 2.7.4`

`rvm use 2.7.4`

### Ejecuta un bundle especifico para una versión de Ruby

Puede darse el caso que nuestro sistema operativo posea su propia versión de Ruby y con ello que se haya configurado la variable PATH para su propio bundle, si ese es el caso podemos llamar un bundle especifico apuntando a la carpeta de la versión de Ruby, de la siguiente manera:

`~/.rvm/gems/ruby-2.7.4/wrappers/bundle install`

Si notaste algún error o recomendación no dudes en comentar.
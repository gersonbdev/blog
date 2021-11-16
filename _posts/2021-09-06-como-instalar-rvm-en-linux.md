---
title: Cómo instalar RVM en Linux
date: 2021-09-06 20:00:00 -0500
categories: [tutoriales]
tags: [linux, ruby]
---

RVM es una herramienta de linea de comando, que permite fácilmente instalar, manejar y trabajar con múltiples entornos de Ruby. Para instalarlo siga los siguientes pasos:

## Instalación de dependencias

* Fedora

```console
$ sudo dnf install gnupg2 curl
```

* Ubuntu

```console
$ sudo apt install gnupg2 curl
```

## Instalación de las llaves GPG

Para la verificación de los paquetes sera necesario la instalación de las siguientes llaves:

```console
$ gpg2 --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
```

## Instalación de RVM con Ruby

El siguiente comando instala la versión estable de RVM junto a la ultima versión de Ruby.

```console
$ \curl -sSL https://get.rvm.io | bash -s stable --ruby
```

### Configuración de la instalación

```console
$ source $HOME/.rvm/scripts/rvm
```

Reinicie su equipo para recargar los cambios en la variable PATH.

## Instalación de una versión diferente de Ruby

Si desea instalar una versión diferente a la predeterminada puede hacerlo como se muestra en el siguiente ejemplo (en este caso instalando la versión 2.7.4):

```console
$ rvm install 2.7.4
```

Para seleccionar la versión instalada escriba:

```console
$ rvm use 2.7.4
```

### Ejecución de un bundle especifico para una versión de Ruby

En caso de que su sistema operativo posea su propia versión de Ruby y con ello que se haya configurado la variable PATH para su propio bundle, puede llamar un bundle especifico apuntando a la carpeta de la versión que desea de Ruby, de la siguiente manera:

```console
$ ~/.rvm/gems/ruby-2.7.4/wrappers/bundle install
```

En este caso se ejecuta el comando `bundle install` usando la versión 2.7.4 como ejemplo.
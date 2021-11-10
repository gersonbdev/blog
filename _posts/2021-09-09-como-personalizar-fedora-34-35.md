---
title: Cómo personalizar Fedora 34/35
date: 2021-09-09 00:35:00 -0500
categories: [tutoriales]
tags: [linux, fedora]
---

Este es un breve tutorial para la personalización de Fedora Linux, donde se modificara tanto la interfaz de GNOME como su comportamiento, además de la personalización de la apariencia del arranque (GRUB).

## Habilita la gestión e integración de extensiones en GNOME

Para instalar extensiones para nuestro entorno desde el navegador y administrarlas es necesario instalar los siguientes paquetes:

```console
$ sudo dnf -y install gnome-extensions-app chrome-gnome-shell
```

Luego de la instalación, entraremos a [GNOME Extensions](https://extensions.gnome.org/) para instalar la extensión nativa del navegador.

### Instala Tray Icons: Reloaded

![Tray Icons: Reloaded screenshot](https://extensions.gnome.org/extension-data/screenshots/screenshot_2890.png)

Para habilitar los iconos en la bandeja superior, podemos instalar la extensión [Tray Icons: Reloaded](https://extensions.gnome.org/extension/2890/tray-icons-reloaded/), para ello solo debemos habilitar el botón de activación en su entrada de *GNOME Extensions*.

## Instala la herramienta de retoques

Esta herramienta te permitirá seleccionar los temas e iconos que instalaremos mas adelante.

```console
$ sudo dnf -y gnome-tweaks
```

## Instala un tema para las aplicaciones

En este caso instalaremos el tema [Mojave](https://github.com/vinceliuice/Mojave-gtk-theme), si lo deseas puedes encontrar mas temas en [GNOME Look](https://www.gnome-look.org/).

### Instala las dependencias del tema Mojave

```console
$ sudo dnf -y install gtk2-engines sassc optipng inkscape glib2-devel
```

### Instala el tema Mojave

![Mojave screenshot](https://raw.githubusercontent.com/vinceliuice/Mojave-gtk-theme/images/screenshot01.jpeg)

Para la instalación del tema entramos en una terminal y descargamos el tema de la siguiente manera:

```console
$ git clone https://github.com/vinceliuice/Mojave-gtk-theme.git
```

Instalamos el tema:

```console
$ cd Mojave-gtk-theme
```


```console
$ ./install.sh
```

Borramos el directorio:

```console
$ cd ..
```


```console
$ rm -rf Mojave-gtk-theme
```

Ya instalado, nos dirigimos al apartado de *apariencia* de la aplicación ***retoques*** donde podremos seleccionar el tema.

En caso de que también desees activar el tema de *GNOME Shell*, dirígete a la aplicación ***extensiones*** y activa *User Themes* para habilitarlo en ***retoques***.

![Icono de inicio de Fedora 01](/assets/img/posts/2021/icon-start-here-fedora-symbolic-01.svg)
![Icono de inicio de Fedora 02](/assets/img/posts/2021/icon-start-here-fedora-symbolic-02.svg)
![Icono a color de inicio de Fedora](/assets/img/posts/2021/icon-start-here-fedora-symbolic-color-01.svg)

Si deseas cambiar la manzana del tema en el panel por el logo de Fedora, descarga los anteriores iconos y reemplazalos por los iconos del tema en la carpeta correspondiente (por ejemplo `/.themes/Mojave-light/gnome-shell/assets`).

## Instala un pack de iconos

![Elemantary default app icon](https://raw.githubusercontent.com/elementary/icons/master/apps/64/application-default-icon.svg)
![Elemantary locale preferences icon](https://raw.githubusercontent.com/elementary/icons/master/categories/64/preferences-desktop-locale.svg)
![Elemantary terminal app icon](https://raw.githubusercontent.com/elementary/icons/master/apps/64/utilities-terminal.svg)

Haremos uso del tema de [iconos de elementary OS](https://github.com/elementary/icons), para su instalacion escribiremos lo siguiente en la terminal:

```console
$ sudo dnf -y elementary-icon-theme
```

Ahora lo seleccionamos dentro de la aplicación ***retoques*** (en este caso podemos seleccionar tanto iconos como cursores).

## Personaliza el arranque (GRUB)

![sleek theme screenshot](https://raw.githubusercontent.com/sandesh236/sleek--themes/master/images/orange.png)

Para conseguir temas puedes dirigirte a [GNOME Look](https://www.gnome-look.org/browse?cat=109&ord=rating), en este caso instalaremos los temas de [sleek](https://github.com/sandesh236/sleek--themes), para ello abre una terminal y escribe:

```console
$ git clone https://github.com/sandesh236/sleek--themes.git
```


```console
$ cd sleek--themes
```

![sleek theme dark](/assets/img/posts/2021/screenshot-sleek-theme-dark.png){: width="240" height="135" }
_Sleek theme-dark_
![sleek theme bigsur](/assets/img/posts/2021/screenshot-sleek-theme-bigsur.png){: width="240" height="135" }
_Sleek theme-bigSur_
![sleek theme light](/assets/img/posts/2021/screenshot-sleek-theme-light.png){: width="240" height="135" }
_Sleek theme-white_
![sleek theme orange](/assets/img/posts/2021/screenshot-sleek-theme-orange.png){: width="240" height="135" }
_Sleektheme-orange_

Reemplaza `theme` del siguiente comando por el tema que desees (cópialo de los pies de las anteriores imágenes):

```console
$ cd theme
```

Ejecuta el instalador del tema y sigue las instrucciones:

```console
$ sudo ./install.sh
```

Ahora borramos los archivos descargados:

```console
$ cd ../..
```


```console
$ rm -rf sleek--themes
```

Ahora reinicia y disfruta de la nueva apariencia de tu entorno de escritorio.
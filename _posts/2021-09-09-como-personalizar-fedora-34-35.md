---
title: Cómo personalizar Fedora 34/35
date: 2021-09-09 00:35:00 -0500
categories: [tutoriales]
tags: [linux, fedora]
image:
  src: /assets/img/posts/2021/banner-fedora-logo-01.png
  width: 1280
  height: 720
  alt: Fedora banner
---

Este es un breve tutorial para la personalización de Fedora Linux, donde se modificara tanto la interfaz de GNOME como su comportamiento, además de la personalización de la apariencia del arranque (GRUB).

## Habilitación de la gestión de extensiones en GNOME

Para instalar extensiones en el entorno desde el navegador y administrarlas es necesario instalar los siguientes paquetes:

```console
$ sudo dnf -y install gnome-extensions-app chrome-gnome-shell
```

Luego de la instalación, entre a [GNOME Extensions](https://extensions.gnome.org/) e instale la extensión nativa del navegador.

### Habilitación de iconos en bandeja

![AppIndicator and KStatusNotifierItem Screenshot](/assets/img/posts/2022/screenshot-appindicator-and-kstatusnotifieritem-001.png)

Para habilitar los iconos en la bandeja superior, es necesario instalar alguna *extensión de GNOME* que lo permita, para ello diríjase a [GNOME Extensions](https://extensions.gnome.org/) e instale la extensión [AppIndicator and KStatusNotifierItem Support](https://extensions.gnome.org/extension/615/appindicator-support/) habilitando el botón de activación de la pagina.

> **📌 Nota:** Esta extensión es la misma que usa Ubuntu en su escritorio.

## Instalación de la herramienta retoques

Esta herramienta le permitirá seleccionar los temas e iconos que se instalaran mas adelante.

```console
$ sudo dnf -y install gnome-tweaks
```

## Instalación de un tema para las aplicaciones

En este caso, se instalara el tema [Mojave](https://github.com/vinceliuice/Mojave-gtk-theme), si lo deseas puede encontrar mas temas en [GNOME Look](https://www.gnome-look.org/).

### Instalación de las dependencias del tema Mojave

```console
$ sudo dnf -y install gtk2-engines sassc optipng inkscape glib2-devel
```

### Instalación del tema Mojave

![Mojave screenshot](https://raw.githubusercontent.com/vinceliuice/Mojave-gtk-theme/images/screenshot01.jpeg)

Para la instalación del tema entre en una terminal y descargue el tema de la siguiente manera:

```console
$ git clone https://github.com/vinceliuice/Mojave-gtk-theme.git
```

Instale el tema:

```console
$ cd Mojave-gtk-theme
```


```console
$ ./install.sh
```

Borre el directorio:

```console
$ cd ..
```


```console
$ rm -rf Mojave-gtk-theme
```

Ya instalado, diríjase al apartado de *apariencia* de la aplicación ***retoques*** donde podra seleccionar el tema.

En caso de que también desee activar el tema de *GNOME Shell*, diríjase a la aplicación ***extensiones*** y active *User Themes* para habilitarlo en ***retoques***.

![Icono de inicio de Fedora 01](/assets/img/posts/2021/icon-start-here-fedora-symbolic-01.svg)
![Icono de inicio de Fedora 02](/assets/img/posts/2021/icon-start-here-fedora-symbolic-02.svg)
![Icono a color de inicio de Fedora](/assets/img/posts/2021/icon-start-here-fedora-symbolic-color-01.svg)

Si desea cambiar la manzana del tema en el panel por el logo de Fedora, descargue los anteriores iconos y reemplacelos por los iconos del tema en la carpeta correspondiente (por ejemplo `/.themes/Mojave-light/gnome-shell/assets`).

## Instalación de un pack de iconos

![Elemantary default app icon](https://raw.githubusercontent.com/elementary/icons/master/apps/64/application-default-icon.svg)
![Elemantary locale preferences icon](https://raw.githubusercontent.com/elementary/icons/master/categories/64/preferences-desktop-locale.svg)
![Elemantary terminal app icon](https://raw.githubusercontent.com/elementary/icons/master/apps/64/utilities-terminal.svg)

Se hará uso del tema de [iconos de elementary OS](https://github.com/elementary/icons), para su instalación escriba en una terminal:

```console
$ sudo dnf -y install elementary-icon-theme
```

Ahora selecciónelo dentro de la aplicación ***retoques*** (en este caso puede seleccionar tanto iconos como cursores).

## Personalización del arranque (GRUB)

![sleek theme screenshot](https://raw.githubusercontent.com/sandesh236/sleek--themes/master/images/orange.png)

> **📌 Nota:** Si su sistema usa EFI es posible que sea necesario comentar la linea `GRUB_TERMINAL_OUTPUT="console"` del archivo `/etc/default/grub` y que construya nuevamente el archivo grub.cfg escribiendo `grub2-mkconfig -o /boot/efi/EFI/fedora/grub.cfg` en una terminal.

Para conseguir temas puedes dirigirse a [GNOME Look](https://www.gnome-look.org/browse?cat=109&ord=rating), en este caso se instalara los temas de [sleek](https://github.com/sandesh236/sleek--themes), para ello abra una terminal y escriba:

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

Reemplace `theme` del siguiente comando por el tema que desee (cópielo de los pies de las anteriores imágenes):

```console
$ cd theme
```

Ejecute el instalador del tema y siga las instrucciones:

```console
$ sudo ./install.sh
```

Borre los archivos descargados:

```console
$ cd ../..
```


```console
$ rm -rf sleek--themes
```

Y con ello habrá finalizado la personalización general del sistema.

---
title: Como personalizar Visual Studio Code
date: 2021-10-24 22:30:00 -0500
categories: [tutoriales]
tags: [linux, fedora]
image:
  src: /assets/img/posts/2021/banner-fedora-logo-01.png
  width: 1280
  height: 720
  alt: Fedora banner
---

## Actualiza el sistema

```terminal
$ sudo dnf -y update
```

## Añade los repositorios extras

### RPMFusion

Para habilitar el soporte de paquetes con licencias propietarias es buena idea agregar los repositorios de RPMFusion, para ello escribe el siguiente comando: 

```terminal
$ sudo dnf -y install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```

### Flathub

```terminal
$ flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

### Snap

```terminal
$ sudo dnf -y install snapd
```


```terminal
$ sudo ln -s /var/lib/snapd/snap /snap
```

Reinicia tu sistema para recargar la variable de entorno PATH.

## Instala los códecs multimedia

```terminal
$ sudo dnf -y install gstreamer1-plugins-{bad-\*,good-\*,base} gstreamer1-plugin-openh264 gstreamer1-libav --exclude=gstreamer1-plugins-bad-free-devel
```


```terminal
$ sudo dnf -y install lame\* --exclude=lame-devel
```


```terminal
$ sudo dnf -y group upgrade --with-optional Multimedia
```

## Instala el soporte de compresión/descompresión

```terminal
$ sudo dnf -y install zip unzip unrar p7zip p7zip-plugins bzip2
```

## Instala Java

```terminal
$ sudo dnf -y install java
``` 

## Instala las fuentes tipográficas de Microsoft

```terminal
$ sudo dnf -y install curl cabextract xorg-x11-font-utils fontconfig
```


```terminal
$ rpm -i https://downloads.sourceforge.net/project/mscorefonts2/rpms/msttcore-fonts-installer-2.6-1.noarch.rpm
```

## Instala el paquete de idioma español para LibreOffice

```terminal
$ sudo dnf -y install libreoffice libreoffice-langpack-es
```

## Personaliza el entorno de escritorio GNOME

Para personalizar el entorno de escritorio puedes dirigirte a la siguiente publicación:

[Cómo personalizar Fedora 34/35](https://gersonbdev.github.io/posts/2021/09/como-personalizar-fedora-34-35/)

## Habilita la interfaz del cortafuegos

```terminal
$ sudo dnf -y install firewalld firewall-config
```

## Instala las herramientas de compilación

En caso de no encontrar el binario de algún paquete es buena idea tener a disposición las siguientes herramientas para realizar la compilación por nosotros mismos:

```terminal
$ sudo dnf -y install kernel-headers kernel-devel
```


```terminal
$ sudo dnf -y groupinstall "Development Tools" "Development Libraries" "C Development Tools and Libraries"
```
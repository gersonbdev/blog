---
title: Qué hacer después de instalar Fedora 34/35
date: 2021-09-09 13:45:00 -0500
categories: [tutoriales]
tags: [linux, fedora]
image:
  src: /assets/img/posts/2021/banner-fedora-logo-01.png
  width: 1280
  height: 720
  alt: Fedora banner
---

Este es un breve tutorial del proceso de post-instalación de la distribución Fedora Linux 34/35. El cual acondiciona el sistema con los paquetes básicos necesarios.

## Actualización del sistema

```console
$ sudo dnf -y update
```

## Adición de repositorios extras

### RPMFusion

Habilite el soporte de paquetes con licencias propietarias, añadiendo los repositorios de RPMFusion. Para ello escriba en una terminal: 

```console
$ sudo dnf -y install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```

### Flathub

Fedora de manera predeterminada hace uso del gestor de paquetes *Flatpak*, lo que le permite instalar aplicaciones contenidas sin tener que preocuparse por las dependencias que estas tengan. Flathub es el principal repositorio para este gestor, teniendo un gran numero de aplicaciones disponibles, para agregarlo puede escribir en una terminal:

```console
$ flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

### Snap

Si necesita software muy especifico empaquetado por Canonical o sus socios (como por ejemplo Flutter), puede ser buena idea agregar Snap como gestor de paquetes en su sistema.

```console
$ sudo dnf -y install snapd
```


```console
$ sudo ln -s /var/lib/snapd/snap /snap
```

Reinicie su sistema para recargar la variable de entorno PATH.

> **📌 Nota:** Tener múltiples gestores de paquetes puede ser poco útil si no necesita de software muy especifico. Tenga en cuenta que Snap actualmente **no** posee soporte con GNOME Software (al menos en lo que respecta a Fedora).

## Instalación de los códecs multimedia

```console
$ sudo dnf -y install gstreamer1-plugins-{bad-\*,good-\*,base} gstreamer1-plugin-openh264 gstreamer1-libav --exclude=gstreamer1-plugins-bad-free-devel
```


```console
$ sudo dnf -y install lame\* --exclude=lame-devel
```


```console
$ sudo dnf -y group upgrade --with-optional Multimedia
```

## Instalación del soporte de compresión/descompresión

```console
$ sudo dnf -y install zip unzip unrar p7zip p7zip-plugins bzip2
```

## Instalación de Java

```console
$ sudo dnf -y install java
``` 

## Instalación de las fuentes tipográficas de Microsoft

```console
$ sudo dnf -y install curl cabextract xorg-x11-font-utils fontconfig
```


```console
$ sudo rpm -i https://downloads.sourceforge.net/project/mscorefonts2/rpms/msttcore-fonts-installer-2.6-1.noarch.rpm
```

## Instalación del paquete de idioma español para LibreOffice

```console
$ sudo dnf -y install libreoffice libreoffice-langpack-es
```

## Personalización del entorno de escritorio GNOME

Puede personalizar el entorno de escritorio dirigiéndose al siguiente enlace:

[Cómo personalizar Fedora 34/35](https://gersonbdev.github.io/posts/2021/09/como-personalizar-fedora-34-35/)

## Habilitación de interfaz grafica del cortafuegos

```console
$ sudo dnf -y install firewalld firewall-config
```

## Instalación de las herramientas de compilación

En caso de no encontrar el binario de algún paquete es buena idea tener a disposición las siguientes herramientas para realizar la compilación por usted mismo:

```console
$ sudo dnf -y install kernel-headers kernel-devel
```


```console
$ sudo dnf -y groupinstall "Development Tools" "Development Libraries" "C Development Tools and Libraries"
```
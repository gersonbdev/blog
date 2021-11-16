---
title: Cómo instalar React Native en Linux
date: 2021-09-06 15:10:00 -0500
categories: [tutoriales]
tags: [linux, javascript]
---

React Native es un framework de código abierto para la creación de aplicaciones móviles multiplataforma, el cual hace uso de tecnologías web para el desarrollo, fundamentándose en JavaScipt. Para instalarlo siga los siguientes pasos:

## Instalación de dependencias

### Instalación de Java

Es necesaria la instalación de Java para ejecutar proyectos de React Native sobre Android, para ello ejecute:

* Fedora

```console
$ sudo dnf -y install java
```

* Ubuntu

```console
$ sudo apt install default-jre
```

## Instalación de snapd

En este caso se hará uso de snapd, ya que permite tener los paquetes estables mas recientes independientemente de la distribución (también puede utilizar su gestor de paquetes nativo si así lo desea), para su instalación siga las instrucciones del siguiente enlace:

[Instalación de snapd](https://snapcraft.io/docs/installing-snapd)

> **📌 Nota:** Si posee Ubuntu puede ignorar esta instalación.

## Instalación de Node.js usando snapd

```console
$ sudo snap install node --channel=16/stable --classic
```

### Actualización de npm

```console
$ sudo npm install -g npm
```

## Instalación de React Native

```console
$ sudo npm install -g react-native-cli
```

## Instalación de Android Studio usando snapd

```console
$ sudo snap install android-studio --classic
```

### Habilitación de las herramientas de linea de comando

Abra Android Studio y diríjase a `More Actions >> SDK Manager >>  SDK Tools` y habilite `Android SDK Command-line Tools (latest)`.

### Configuración de la variable de entorno PATH

Diríjase a su carpeta personal (`/home/usuario`) y habilite los elementos ocultos (puede hacerlo pulsando `Ctrl + h`), luego abra el archivo `.bash_profile` y agregue el siguiente código:

```bash
# Setting the ANDROID_HOME environment variable

export ANDROID_HOME="$HOME/Android/Sdk"
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH="$PATH:$ANDROID_HOME/tools"
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH="$PATH:$ANDROID_HOME/platform-tools"
```

> **📌 Nota:** Puede entrar directamente desde la terminal escribiendo `gedit $HOME/.bash_profile`.

Ahora, reinicie su equipo para cargar los cambios.

## Verificación de la instalación

### Creación de un nuevo proyecto

```console
$ react-native init MyApp
```


```console
$ cd ./MyApp/
```


```console
$ react-native start
```

### Ejecución del proyecto

Cree un dispositivo en Android Studio para simular la aplicación, luego abra una nueva terminal en la ruta del proyecto (`./MyApp/`) y escriba:

```console
$ react-native run-android
```

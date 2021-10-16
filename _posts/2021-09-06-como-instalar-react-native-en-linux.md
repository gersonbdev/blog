---
title: Cómo instalar React Native en Linux
date: 2021-09-06 15:10:00 -0500
categories: [tutoriales]
tags: [linux, javascript]
---

React Native es un framework de código abierto para la creación de aplicaciones móviles multiplataforma, el cual hace uso de tecnologías web para el desarrollo, fundamentándose en JavaScipt.

Los siguientes pasos permiten la instalación de React Native en cualquier distribución de GNU/Linux.

## Instala snapd

En este caso haremos uso de snapd, ya que nos permitirá tener los paquetes estables mas recientes independientemente de la plataforma, para su instalación sigue las instrucciones del siguiente enlace:

[Instalación de snapd](https://snapcraft.io/docs/installing-snapd)

## Instala Node.js usando snapd

```terminal
$ sudo snap install node --classic
```

### Actualiza npm

```terminal
$ sudo npm install -g npm
```

## Instala React Native

```terminal
$ sudo npm install -g react-native-cli
```

## Instala Android Studio usando snapd

```terminal
$ sudo snap install android-studio --classic
```

### Habilita las herramientas de linea de comando
Abre Android Studio y dirígete a `More Actions >> SDK Manager >>  SDK Tools` y habilita `Android SDK Command-line Tools (latest)`.

### Configura la variable de entorno PATH

Dirígete a tu carpeta personal `/home/usuario` habilita los elementos ocultos (Ctrl + h) y en el archivo `.bash_profile` (puedes entrar directamente desde la terminal escribiendo `gedit $HOME/.bash_profile`) agrega el siguiente código:

```bash
# Setting the ANDROID_HOME environment variable

export ANDROID_HOME="$HOME/Android/Sdk"
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH="$PATH:$ANDROID_HOME/tools"
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH="$PATH:$ANDROID_HOME/platform-tools"
```

Ahora, reinicia tu equipo para cargar los cambios.

## Verificación de instalación

### Crea un nuevo proyecto

```terminal
$ react-native init MyApp
```


```terminal
$ cd ./MyApp/
```


```terminal
$ react-native start
```

### Ejecuta el proyecto

Crea un dispositivo en Android Studio para simular la aplicación, luego abre una nueva terminal en la ruta del proyecto (./MyApp/) y escribe:

```terminal
$ react-native run-android
```

---
title: Cómo instalar React Native en Linux
date: 2021-09-06 15:10:00 -0500
categories: [tutoriales]
tags: [linux, javascript]
---

React Native es un framework de código abierto para la creación de aplicaciones móviles multiplataforma, el cual hace uso de tecnologías web para el desarrollo, fundamentándose en JavaScipt.

Los siguientes pasos permiten la instalación de React Native en cualquier distribución de GNU/Linux.

## Instalar snapd

En este caso haremos uso de snapd, ya que nos permitirá tener los paquetes estables mas recientes independientemente de la plataforma, para su instalación sigue las instrucciones del siguiente enlace:

[Instalación de snapd](https://snapcraft.io/docs/installing-snapd)

## Instalar Node.js usando snapd

`sudo snap install node --classic`

## Instalar React Native

`sudo npm install -g react-native-cli`

## Instalar Android Studio usando snapd

`sudo snap install android-studio --classic`

### Habilitar herramientas de linea de comando
Abre Android Studio y dirígete a `More Actions >> SDK Manager >>  SDK Tools` y habilita `Android SDK Command-line Tools (latest)`.

### Configurar variable de entorno PATH

Ejecuta los siguientes comandos en la terminal (uno por uno):

``echo 'export ANDROID_HOME="$HOME/Android/Sdk"' >> ~/.profile``

``echo 'export PATH="$PATH:$ANDROID_HOME/tools"' >> ~/.profile``

``echo 'export PATH="$PATH:$ANDROID_HOME/platform-tools"' >> ~/.profile``

Ahora, reinicia tu equipo para cargar los cambios.

## Verificación de instalación

### Crea un nuevo proyecto

`react-native init MyApp`

`cd ./MyApp/`

`react-native start`

### Ejecuta el proyecto

Crea un dispositivo en Android Studio para simular la aplicación, luego abre una nueva terminal en la ruta del proyecto (./MyApp/) y escribe:

`react-native run-android`
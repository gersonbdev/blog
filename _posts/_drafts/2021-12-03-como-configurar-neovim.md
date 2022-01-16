---
title: Como configurar Vim/Neovim
date: 2021-09-09 13:45:00 -0500
categories: [tutoriales]
tags: [linux, fedora]
image:
  src: /assets/img/posts/2021/banner-fedora-logo-01.png
  width: 1280
  height: 720
  alt: Fedora banner
---

## Instalación de vim-plug

### Vim

#### Unix

```sh
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

You can automate the process by putting the command in your Vim configuration
file as suggested [here][auto].

[auto]: https://github.com/junegunn/vim-plug/wiki/tips#automatic-installation

#### Windows (PowerShell)

```powershell
iwr -useb https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim |`
    ni $HOME/vimfiles/autoload/plug.vim -Force
```

### Neovim

#### Unix, Linux

```sh
sh -c 'curl -fLo "${XDG_DATA_HOME:-$HOME/.local/share}"/nvim/site/autoload/plug.vim --create-dirs \
       https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim'
```

#### Linux (Flatpak)

```sh
curl -fLo ~/.var/app/io.neovim.nvim/data/nvim/site/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

#### Windows (PowerShell)

```powershell
iwr -useb https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim |`
    ni "$(@($env:XDG_DATA_HOME, $env:LOCALAPPDATA)[$null -eq $env:XDG_DATA_HOME])/nvim-data/site/autoload/plug.vim" -Force
```

> **📌 Nota:** 

## Vincular Neovim con Vim

Crear directorio `~/.config/nvim/`

```console
$ ln -s ~/.vimrc ~/.config/nvim/init.vim
```

## Configura Vim/Neovim
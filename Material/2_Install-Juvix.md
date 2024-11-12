# Install Juvix

<img alt="tara mascot smiling" width="400" src="../.assets/tara-smiling.png">
<p>
  <a href="https://discord.gg/PfaaFVErHt"><img src="https://img.shields.io/discord/952881043520774194?logo=discord"/></a>
</p>

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/anoma/juvix-workshop?quickstart=1)

## Table of Contents

- [Introduction](#introduction)
- [Installing Juvix](#installing-juvix)
- [IDE Setup](#ide-setup)
  - [VSCode](#vscode)
  - [Emacs](#emacs)
- [Juvix Documentation](#juvix-documentation)

## Introduction

Welcome to Juvix!

## Installing Juvix

Please use one of the following options to install the Juvix compiler. Juvix is
supported on Linux x86_64 and macOS x86_64 or aarch64 (M1/M2).

### Prerequisites

The Juvix compiler requires [the LLVM/clang compiler](https://llvm.org) to be available on your system PATH in order to build native binaries.

### macOS homebrew

If you use the [Homebrew package manager](https://brew.sh) you can use our tap:

```shell
brew update
brew tap anoma/juvix
brew install juvix
```

### Linux / macOS automatic installer

To install for linux or macOS run the following in a terminal (as a non-root user):

```shell
curl --proto '=https' --tlsv1.2 -sSfL https://get.juvix.org | sh
```

### Manual installation

There are also binaries for the Juvix compiler available to download

| OS / Architecture                                                                                           |
| ----------------------------------------------------------------------------------------------------------- |
| [Linux x86_64](https://github.com/anoma/juvix/releases/latest/download/juvix-linux-x86_64.tar.gz)           |
| [macOS x86_64](https://github.com/anoma/juvix/releases/latest/download/juvix-macos-x86_64.tar.gz)           |
| [macOS aarch64 (M1/M2)](https://github.com/anoma/juvix/releases/latest/download/juvix-macos-aarch64.tar.gz) |

## IDE Setup

### Visual Studio Code

First install visual studio code from the Microsoft website https://code.visualstudio.com/download

In the extension tab search for `juvix` and install the extension that features the Tara logo.

See the [vscode-juvix repository](https://github.com/anoma/vscode-juvix) for usage information.

### Emacs

To get started, clone the [juvix-mode repository](https://github.com/anoma/juvix-mode.git)

```shell
git clone https://github.com/anoma/juvix-mode.git
```

And add the following lines to your Emacs configuration file:

```emacs-lisp
(push "/path/to/juvix-mode/" load-path)
(require 'juvix-mode)
```

See the [juvix-mode repository](https://github.com/anoma/juvix-mode.git) for usage information.

## Juvix Documentation

The full documentation for Juvix is available at https://docs.juvix.org

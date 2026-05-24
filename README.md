# JAnsi Fixed for Termux

(Português do Brasil no final)

Fixing JAnsi Error in Termux (Kotlin/Java)

This repository contains the solution for the JAnsi native library error (org.fusesource.jansi.AnsiMain) that occurs when trying to run Kotlin or Gradle within the Termux environment on Android.


The Problem:

When running Java/Kotlin development tools in Termux, the system attempts to load a native JAnsi library to handle terminal colors. Because the Android environment has different directory paths and permissions than a standard Linux distribution, this loading fails and blocks command execution.


The Solution:

1. Download the fixed JAR
Download the jansi-2.4.4-SNAPSHOT.jar file from this repository directly to your device using Termux. You can use curl or wget to get the file.

2. Add permanently to your environment
To route Java through the fix and prevent Kotlin/Gradle from crashing, add the following configuration lines to your terminal file (~/.bashrc or ~/.zshrc):

export KOTLIN_OPTS="-Djansi.passthrough=true"
export JAVA_OPTIONS="-Djansi.passthrough=true"

---

Correção do Erro JAnsi no Termux (Kotlin/Java)

Este repositório registra a solução para o erro de biblioteca nativa do JAnsi (org.fusesource.jansi.AnsiMain) que ocorre ao tentar executar o Kotlin ou o Gradle dentro do ambiente Termux no Android.


O Problema:

Ao rodar ferramentas de desenvolvimento Java/Kotlin no Termux, o sistema tenta carregar uma biblioteca nativa do JAnsi para processar cores no terminal. Como o ambiente Android possui caminhos e permissões diferentes de um Linux tradicional, o carregamento falha e impede a execução dos comandos.


A Solução:

1. Baixar o arquivo JAR corrigido
Baixe o arquivo jansi-2.4.4-SNAPSHOT.jar deste repositório diretamente no seu dispositivo usando o Termux. Você pode utilizar o comando curl ou wget para obter o arquivo.

2. Adicionar permanentemente ao seu ambiente
Para direcionar o Java através da correção e evitar que o Kotlin/Gradle parem de funcionar, adicione as seguintes linhas de configuração ao arquivo do seu terminal (~/.bashrc ou ~/.zshrc):

export KOTLIN_OPTS="-Djansi.passthrough=true"
export JAVA_OPTIONS="-Djansi.passthrough=true"

# Tutorial Bash - nível iniciante  

![*Tux, the Linux penguin*](imagens/tux.png)  

## Introdução  

Este tutorial é um jogo caça-letras para ajudar usuários iniciantes em Linux a se familiarizarem com a _Command Line Interface_ (CLI), ou **[shell](https://pt.wikipedia.org/wiki/Shell_(computa%C3%A7%C3%A3o))**, mais especificamente com o **[bash](https://pt.wikipedia.org/wiki/Bash)**, um interpretador de comandos shell.  

Este tutorial é uma adaptação do tutorial **[bash_tutorial](https://github.com/krother/bash_tutorial)** de Kristian Rother.  

### Para quem é este tutorial?  

Para todos que tem pouca ou nenhuma experiência com o **bash**  

### O que você alcançará ao completar este tutorial?  

Conhecimento sobre comandos para:  

* Navegar entre diretórios  
* Criar e manipular arquivos de texto  
* Baixar arquivos da internet  
* Compactar e descompactar arquivos  
* Executar scripts  
* Argumentos e parâmetros dos comandos  

### Pré-requesitos  

Este tutorial foi elaborado e implementado em uma Distribuição Linux baseado em Debian. Desta forma, espera-se que qualquer [distribuição baseada em Debian](https://distrowatch.com/search.php?ostype=Linux&basedon=Debian) seja o suficiente para completá-lo.

## Objetivo  

Você deverá encontrar os 23 caracteres escondidos neste repositório utilizando vários comandos **shell**. Estes caracteres formam uma frase com duas palavras e um espaço em branco entre elas.  

![*disposição dos 23 caracteres*](imagens/caca_letras.png)


## Preparação inicial

Em uma máquina com uma distribuição Linux, abra o terminal. Muito provavelmente você estará no diretório de trabalho chamado de _home do usuário_, indicado pela linha:  
``` {.sourceCode .bash}
<usuário>@<máquina>:~$
```

O termo **<usuário\>** é o nome do usuário logado no momento. Em computadores de escolas, normalmente os técnicos de informática escolhem **aluno**, **usuário** ou qualquer outro **nome genérico**, mas se você estiver em um computador seu ou da sua família, este nome deve ser um nome reconhecido por você.  

Na sequência, o termo **<máquina\>** é o nome do computador que você está usando, podendo ser nomes bem variados e criativos.

Para a coerência deste jogo, toda vez que for necessário apresentar a linha de comando completa, será usado estes dois termos genéricos **<usuário\>** e **<máquina\>**.

para garantir que você está no diretório _home do usuário_ entre com o seu primeiro comando:  
Observação: para executar um comando, digite-o e pressione **enter**
``` {.sourceCode .bash}
usuário@máquina:~$ pwd
```  
Deverá ser apresentado a seguinte resposta:
``` {.sourceCode .bash}
/home/usuário
```

Após verificado estas condições inicias, vamos começar nossa caçada às letras.

## 1. Baixar arquivo da internet e Descompactá-lo  

### 1.1 Baixar o arquivo tutorial_bash_nv01.zip

Vamos baixar a estrutura de diretórios e arquivos deste repositório utilizando o comando **wget**.  
Este comando é um _downloader_ que aceita como argumento uma [URI](https://pt.wikipedia.org/wiki/URL). Neste caso, como desejamos baixar a estrutura de diretórios do nosso repositório, usaremos a URI do arquivo compactado como este argumento. Desta forma, no terminal, entre com o seguinte comando:
``` {.sourceCode .bash}
wget https://github.com/bellorini/tutorial_bash_nv01/archive/refs/heads/tutorial_bash_nv01.zip
```

TODO, apresentar texto de completado após completar a construção deste tutorial  

O arquivo baixado chama-se **tutorial_bash_nv01.zip**. Para verificar se este arquivo foi baixado, use o comando **ls**.  
Este comando lista o conteúdo de um diretório.
``` {.sourceCode .bash}
usuário@máquina:~$ ls
```  

É possível que apareçam muitos outros arquivos, porém, o arquivo **tutorial_bash_nv01.zip** deve estar presente.

### 1.2 Descompactar o arquivo tutorial_bash_nv01.zip  

O arquivo baixado está no formato [zip](https://pt.wikipedia.org/wiki/ZIP). Estes arquivos agrupam (empacotam) e compactam outros arquivos. 

TODO  
* listar conteúdo de arquivo compactado  
* descompactar zip  












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
Observação 1: para executar um comando, digite-o e pressione **ENTER**
``` {.sourceCode .bash}
usuário@máquina:~$ pwd # pressione ENTER
```  
Deverá ser apresentado a seguinte resposta:
``` {.sourceCode .bash}
/home/usuário
```

Observação 2: em alguns momento será necessário adicionar um ou outro comentário, desta forma, o caractere **#** será utilizado, portanto, tudo o que estiver à direita do **#** é um comentário e não deve ser entrado no terminal. Um exemplo de uso de comentário é observado acima, junto ao comando **pwd**

Observação 3: em casos onde não é necessário apresentar a linha de comando completa, todas as informações entre o início da linha de comando até o caractere "$" serão ocultados, por exemplo:
``` {.sourceCode .bash}
$ pwd 
```  

Obsevação 4: espaço em branco é muito importante no terminal, já que este é considerado um separador de campos. Assim, deve-se sempre inserir um espaço em branco entre o comando e seus parâmetros e argumentos

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

O comando **unzip** é utilizado para, entre outras coisas, listar o conteúdo de um arquivo compactado e descompactar este pacote.  
Inicialmente, vamos listar o conteúdo do pacote **tutorial_bash_nv01.zip** com a seguinte linha de comando:
``` {.sourceCode .bash}
usuário@máquina:~$ unzip -l tutorial_bash_nv01.zip
```  

Será apresentado uma tabela com uma estrutura de diretórios e arquivos, contendo tamanho, data e nome.

A partir deste momento, o dispositivo mouse não deve ser mais necessário, desta forma, __mãos ao teclado__!  
![teclado sim, mouse não](imagens/keymouse.png)  

Observe que o comando **unzip** recebeu um parâmetro **-l** e um argumento **tutorial_bash_nv01.zip**. Mas o que são argumentos e parâmetros?  

* **argumento(s)** são modificadores do comando que alteram a funcionalidade deste. No nosso exemplo, o comando **unzip** apenas lista o conteúdo do pacote sem qualquer outro resultado, como descompactar ou alterá-lo. 
* **parâmetro(s)** são modificadores do comando que indicam os objetos de entrada e/ou saída da funcionalidade executada. Neste caso, o pacote **tutorial_bash_nv01.zip** é o nosso objeto que será listado.  

Agora, para descompactar o pacote **tutorial_bash_nv01.zip** basta entrar com o comando:
``` {.sourceCode .bash}
usuário@máquina:~$ unzip tutorial_bash_nv01.zip
```  

Deverá ser criado um novo diretório chamado **tutorial_bash_nv01** dentro do seu diretório __home__. Para verificar, vamos usar o comando **ls** já conhecido, porém adicionando o argumento **tutorial_** e pressione a tecla **TAB** para autocompletar (o terminal é esperto o suficiente para autocompletar)
``` {.sourceCode .bash}
usuário@máquina:~$ ls tutorial_ #TAB (autocompleta com "bash_nv01")
# resultado após pressionar TAB: 
usuário@máquina:~$ ls tutorial_bash_nv01
```  

## 2. Diretórios e Arquivos

Rumo ao primeiro caractere!  
Recomenda-se ir anotando os caracteres encontrados.

### 2.1 Alterar o diretório atual de trabalho e listar arquivos 

> DICA: o caractere 01 pode ser encontrado no nome de um arquivo em algum lugar do diretório "exercícios/exercício02"

Para navegar entre diretórios e acessar diretórios abaixo na hierarquia, também chamados de diretórios _filhos_ ou _subdiretórios_, utilize o comando **cd** com o argumento __nome do diretório de destino__
``` {.sourceCode .bash}
usuário@máquina:~$ cd # insira o diretório de destino e pressione ENTER
```  

Como resultado, o diretório atual de trabalho será o diretório escolhido e a linha de comando será alterada para  
``` {.sourceCode .bash}
usuário@máquina:~/nome_do_diretório_de_destino$ 
```  

Para voltar ao diretório acima na hierarquia, também chamado de diretório _pai_, use o comando **cd**, porém, como argumento _nome do diretório de destino_, utilize ".." (dois pontos em sequência).
``` {.sourceCode .bash}
usuário@máquina:~/algum_diretório$ cd ..
```  

Como resultado, você alterará o diretório atual de trabalho para o diretório _pai_ do seu diretório atual.

Navegue entre os diretórios filhos do diretório **exercício02** até encontrar o arquivo que contém no nome o caractere escondido.  

### 2.2 Listar arquivos ocultos  

> DICA: o caractere 02 pode ser encontrado no nome de um arquivo oculto e em algum lugar do diretório "exercícios/exercício02"


Arquivos ocultos no Linux são aqueles cujo nome iniciam com um caractere "." (ponto)  

Para listar arquivos ocultos, basta utilizar o parâmetro **-a** no comando **ls**
``` {.sourceCode .bash}
usuário@máquina:~$ ls -a
```  

Como resultado, serão apresentados os arquivos ocultos junto com os arquivos "normais". Normalmente, dentro de cada diretório, encontram-se os diretórios ocultos "." e ".." 

* diretório ".": é uma ligação/ponteiro para o próprio diretório, útil para desambiguação entre comandos locais e globais
* diretório "..": é uma ligação/ponteiro para o diretório _pai_ e já foi usado junto com o comando **cd** na seção 2.1  

### 2.3 Executando um script

> DICA: o caractere 03 será exibido no terminal ao executar o script chamado "um_script.sh" existente em algum subdiretório do diretório exercícios/exercício02/

Um arquivo [script](https://pt.wikipedia.org/wiki/Shell_script) é um arquivo que contém um ou vários comandos **shell** em uma sequência lógica de execução. Estes arquivos são extremamente úteis para tornar ações rotineiras em _scripts_ automáticos.

Uma das formas mais simples de executar um arquivo **script** é utilizar o comando **source** com o argumento sendo o nome do arquivo que contém o script desejado.

``` {.sourceCode .bash}
usuário@máquina:~$ source #nome do arquivo que contém o script, normalmente terminal em .sh
```  

**IMPORTANTE**: scripts da internet podem ser perigosos, sempre certifique-se que a origem do script é segura antes de executá-lo e nunca, jamais, big nop, execute linhas de comando copiadas da internet sem ter um pouco de conhecimento sobre o que estas executam, pois você pode executar algo malicioso. 
> Linha de comando e scripts são ferramentas poderosas que são utilizadas para o bem e também para o mal!

### 2.4 Descobrindo o tamanho de um arquivo com ls


> DICA: o caractere 04 é o caractere ASCII apontado pelo tamanho do arquivo "exercícios/exercício02/qual_é_meu_tamanho_em_bytes.txt"

Até o momento, o comando **ls** foi usado de forma _pura_, sem parâmetros ou argumentos. Porém, este comando pode fazer muitas coisas, e uma delas é mostrar várias informações de arquivos ou um arquivo específico. Estas informações estão relacionadas na forma de uma tabela com as seguintes informações (da esquerda para direita):  

* se é um arquivo ou diretório  
* permissões de acesso ao arquivo (dono/grupo/outros)  
* quem é o dono do arquivo  
* qual é o grupo que o arquivo pertence  
* tamanho do arquivo em bytes  
* _timestamp_  
* nome do arquivo  

Então, para mostrar todas estas informações, use o comando **ls** com o parâmetro **-l** no diretório especificado na _Dica_ acima.
``` {.sourceCode .bash}
usuário@máquina:~/tutorial_bash_nv01$ ls -l exercícios/exercício02/
```  

Após descobrir o tamanho do arquivo "qual_é_meu_tamanho_em_bytes.txt", use a [tabela ASCII](https://en.wikipedia.org/wiki/ASCII#Printable_characters) e relacione o tamanho do arquivo com a coluna DEC e o caractere 04 é o glifo associado à este valor.

## 3. Visualizar e editar arquivos de texto  

Volte para o diretório principal localizado em "/home/usuário/tutorial_bash_nv01/" e acesse o diretório "exercícios/exercício03/"  

### 3.1 Visualizar o conteúdo de um arquivo de texto

> DICA: o caractere 05 está dentro do arquivo "exercício03/o_quinto_caractere_está_aqui.txt"

Para exibir o conteúdo de um arquivo de texto, use o comando **less** com o arquivo desejado como argumento:
``` {.sourceCode .bash}
$ less o_quinto_caractere_está_aqui.txt
```

Como resultado, será exibido uma tela contendo o conteúdo do arquivo uma página de cada vez. O comando **less** permite navegar no texto utilizando as setas de movimentação **cima** e **baixo** do teclado. Porém, o arquivo é pequeno e não é necessário tal ação.  

Após anotar o caractere 05, use a tecla Q para encerrar o comando **less**  

### 3.2 Editar um arquivo de texto com programa "nano"

Para encontrar o caractere 06, crie um arquivo de texto contendo os cinco caracteres já encontrados. Para criar e editar um arquivo de texto, use o programa [**nano**](https://terminalroot.com.br/2015/10/o-editor-de-texto-nano.html). Estando no diretório "exercício03" entre com o seguinte comando:
``` {.sourceCode .bash}
$ nano caractere06.txt
```

Entre com os caracteres encontrados e use as teclas de atalhos CTRL+X. Será perguntado se você deseja salvar o arquivo, responda de forma afirmativa com o caractere "S" ou "Y" (em inglês). Logo, será perguntado qual é o nome do arquivo, que já estará preenchido, bastando pressionar ENTER. 

> DICA: o caractere 06 é o caractere que foi pressionado para afirmar o salvamento do arquivo (em inglês)

## 4. Criar diretório, copiar e remover arquivos

Volte para o diretório principal localizado em "/home/usuário/tutorial_bash_nv01/" e acesse o diretório "exercícios/exercício04/"  

### 4.1 Criar um diretório  

Liste o conteúdo do diretório "exercício04". Este diretório deve conter 2 subdiretório chamados "solução_parte_01" e "solução_parte_02". Dentro de cada um destes diretórios existe um arquivo de texto.

Crie um subdiretório chamado "solução_completa" dentro deste diretório "exercício04" com o comando **mkdir**. O comando **mkdir**, de _make directory_ aceita um ou mais argumentos, separados com espaço em branco, sendo que cada argumento é o nome do subdiretório que deve ser criado. No caso, basta criar apenas um único diretório.
``` {.sourceCode .bash}
$ mkdir solução_completa
```

Liste novamente o conteúdo do diretório "exercício04" para confirmar a criação deste diretório "solução_completa"

### 4.2 Copiar arquivos

Para encontrar a próxima solução, será necessário copiar os arquivos dos subdiretórios "solução_parte_01" e "solução_parte_02" para o subdiretório criado "solução_completa". Para tal, use o comando **cp**, que aceita dois argumentos:  

* primeiro argumento: é o arquivo de origem que será copiado
* segundo argumento: é o local de destino da cópia

Desta forma, para completar a ação de copiar, identifique os nomes dos arquivos dos subdiretórios e execute 2x o comando **cp**
``` {.sourceCode .bash}
$ cp solução_parte_01/#_arquivo_de_origem solução_completa/
```

e
``` {.sourceCode .bash}
$ cp solução_parte_02/#_arquivo_de_origem solução_completa/
``` 

> DICA: os caractere 07 e caractere 08 estão marcados entre os dois arquivos copiados para o subdiretório "solução_completa". Você deve listá-los com o comando **ls -l** e o segundo arquivo marca com caractere "+" o caractere que será usado como solução no primeiro arquivo, respectivamente como 07 e 08.

### 4.3 Removendo arquivos

No subdiretório "dados" encontram-se vários arquivos com nomes padronizados. Dois destes arquivos não contém o caractere "Y" em seus nomes. Você deve remover todos os arquivos que contém "Y".

> DICA: os caracteres 09 e 10 são os caracteres diferente de "X" nos nomes dos dois arquivos que sobrarem após a remoção de todos os arquivos que contém "Y" em seu nome do subdiretório "dados"

Para remover um arquivo, use o comando **rm** seguido do argumento nome_do_arquivo_a_ser_excluído.
``` {.sourceCode .bash}
$ rm # insira o nome_do_arquivo_a_ser_excluído
```

Outra dica é o caractere curinga __*__ que pode ser usado no terminal. Este caracteres significa "qualquer combinação de caracteres nesta posição", isto é, se você usar a seguinte linha de comando:
``` {.sourceCode .bash}
$ rm *Y
```

Como resultado, removerá TODOS os arquivos que contém qualquer combinação de caracteres e são finalizados com o caractere "Y". Você pode aplicar mais do que um caractere curinga __*__ nas linhas de comando.

**IMPORTANTE**: o caractere curinga é muito poderoso e deve ser usado com cautela. Em Linux, não é possível recuperar um arquivo apagado pelo comando **rm**.

## 5. Processamento básico de textos

Volte para o diretório principal localizado em "/home/usuário/tutorial_bash_nv01/" e acesse o diretório "exercícios/exercício05/"  

### 5.1 Comparando arquivos de texto  

> Dica: o caractere 11 é o único caractere que é diferente entre os arquivos "ai.txt" e "inteligencia_artificial.txt"  

Para comparar 2 arquivos de texto, o comando **diff** é utilizado. Este comando **diff** aceita 2 argumentos que são os arquivos que se deseja comparar.
``` {.sourceCode .bash}
$ diff #arquivo1 #arquivo2
```

Como resultado, será apresentado todas as linhas que diferem entre os arquivos adicionados como argumento.  
Caso queira, e é altamente recomendado, leia o conteúdo do arquivo com **less** ou **nano**.

### 5.2 Verificando se você está prestando atenção neste jogo  

> Dica: o caractere 12 é o caractere separador de parâmetros e argumentos no interpretador "shell"

### 5.3 Ordenando alfabeticamente as linhas de um arquivo de texto  

O interpretador shell contém um comando para ordenar as linhas de um arquivo, chamado **sort**. Este comando recebe como argumento um arquivo e resulta, no próprio terminal, as linhas ordenadas alfabeticamente de forma crescente  

> Dica: o caractere 13 é o primeiro caractere da última palavra da primeira linha do arquivo "elefante.txt" ordenado

Para executar a ordenação em um arquivo, use a seguinte linha de comando:
``` {.sourceCode .bash}
$ sort #arquivo1 
```
Não esqueça de verificar o arquivo original e comparar com o que foi apresentado pelo **sort**

### 5.3 Encontrando palavras dentro de um arquivo de texto

Em algumas ocasiões, você poderá se deparar com a necessidade de procurar algo dentro de um arquivo de texto muito grande. No lugar de abrir o arquivo e o lê-lo por completo, é possível pedir ao comando **grep** para localizar uma palavra que pertença a linha procurada.

``` {.sourceCode .bash}
$ grep #palavra_procurada #arquivo
```

O resultado será uma lista de linhas pertencentes ao arquivo que contém a palavra procurada nestas.

> Dica: o caractere 14 está dentro do arquivo "memorias_enterradas_na_areia.txt". Mais precisamente, é o primeiro caractere da única linha que contém a palavra "happened"  


## 6. Encontrar arquivos

Volte para o diretório principal localizado em "/home/usuário/tutorial_bash_nv01/"  

> Dica: o caractere 15 está na última linha do arquivo que contém o termo "Pascal" em seu nome. Este arquivo está localizado em algum lugar dos subdiretórios de "tutorial_bash_nv01"

**IMPORTANTE**: o nome do arquivo procurado não é somente "Pascal", mas **contém "Pascal"**, desta forma, vale lembrar do uso do caractere curinga __*__ observado no item 4.3

Para procurar um arquivo pelo nome, utilize o comando **find** com o parâmetro **-name="nome_desejado"**
``` {.sourceCode .bash}
$ find -name=#insira aqui o nome desejado entre áspas duplas, e não use espaço entre o = e este nome
```

Após encontrar o arquivo, liste as últimas linhas deste arquivo com o comando **tail**
``` {.sourceCode .bash}
$ tail #local+nome do arquivo desejado
```














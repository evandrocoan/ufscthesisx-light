# Template para ufscthesisx

Modelo Canônico de TCC,
Monografia,  Dissertação,
Tese ou Relatório de Pós--Doutorado da UFSC com abnTeX2.
Originado de endereço https://github.com/AdrianoRuseler/abntex2-ufsc com o nome `abntex2-ufsc`,
este projeto foi renomeado para `ufscthesisx`.

Esse projeto não está vinculado a nenhum órgão da UFSC.

## Modelo em PDF

Se você quer ter uma ideia de como é o modelo,
a compilação deve resultar no seguinte [PDF](https://github.com/evandroforks/abntex2-ufsc-imagens/blob/master/pdf_exemplo_completo.pdf)


## Instalar `LaTeX` e `abnTeX2`

Para poder utilizar a classe é necessário ter uma distribuição atual do LaTeX,
incluindo o pacote abnTeX2.
*Sugerimos formtemente a utilização da distribiução TeX Live para Windows e Linux e MacTeX para macOS*.

As configurações específicas para cada sistema podem ser encontradas nos link abaixo para o pacote `abnTeX2`:
1. [abntex2 CTAN](http://www.ctan.org/pkg/abntex2)
1. [abnTeX2 Instalação](https://github.com/abntex/abntex2/wiki/Instalacao)


### Instalação Ubuntu/Linux Mint and others

```
sudo apt-get install texlive-full
sudo apt-get install xzdec
```


### Instalação Windows

1. Baixe o arquivo do instalador em: https://miktex.org/download
1. Enquando seguindo dos passas do instalador,
   assegure-se de marcar para instalar todos os pacotes latex (full install).


## Baixando diretamente modelo UFSC

Caso queria,
pode baixar diretamente o arquivo `zip` clique
[aqui](https://github.com/UFSC/ufscthesisx/releases/download/v1.1/ufscthesisx.zip) e descompacte o arquivo.


## Utilizando `git` para baixar o modelo USFC

No diretório do seu projeto faça um clone (recursivo) dos arquivos do repositório:
```bash
git clone --recursive https://github.com/ufsc/ufscthesisx
```

Este repositório já contém um exemplo de tese com uso avançado de conceitos e LaTeX.
Se você tiver interesse em utilizar esse **template**,
você precisa preencher os seus dados como nome do orientador,
coorientador, seu nome,
nome da sua instituição,
do seu curso, departamento,
etc.

Para isso altere os dados fictícios para os corretos no arquivo `main.tex`,
que é o arquivo principal do **template** utilizado,
e carrega todos os pacotes necessários e incluir os arquivos LaTeX que contém as partes da sua monografia.


## Utilizando Overleaf para digitar sua tese com modelo UFSC

Se você quiser,
pode utilizar o [Overleaf](www.overleaf.com),
um sistema de editoração *online* de textos em LaTeX.
Se você já tiver uma conta no Overleaf pode fazer o *upload* do arquivo `.zip` baixado acima ou então faça o *upload* automaticamente com a
última versa clicando [aqui](http://overleaf.com/docs?snip_uri=https://github.com/UFSC/ufscthesisx/releases/download/v1.1/ufscthesisx.zip)


# Uso

A ideia é fazer com que você utilize a classe abnTeX2,
mas com customizações voltadas para as normas de trabalhos acadêmicos da UFSC,
fazendo com que o seu uso seja idêntico ao uso direto da classe abnTeX2.

A documentação dessa classe pode ser encontrada nos link a seguir e também é possível
encontrar modelos de documentos que utilizam a classe para tomar como base:
1. [Documentação e Modelos abnTeX2](https://www.ctan.org/pkg/abntex2)

Para compilar este modelo,
você pode utilizar seu editor git favorito,
e pedir para ele compilar o documento a partir do arquivo `main.tex` no diretório principal.

Por conveniência,
você também pode executar o arquivo `build.bat` caso você esteja no Windows,
ou executar o comando `make` caso você esteja no Linux.


## Compilação

O jeito mais legal de compilar é executando um dos seguintes comandos:
1. **`make clean`**
1. **`make clean halt=1 debug=1`**
1. **`make latex biber latex1`**
1. **`make latex biber latex1 halt=1 debug=1`**
1. **`make latex biber latex1 biber1 latex2`**
1. **`make latex biber latex1 biber1 latex2 halt=1 debug=1`**
1. **`make latex biber latex1 biber1 latex2 latex3`**
1. **`make latex biber latex1 biber1 latex2 latex3 halt=1 debug=1`**
1. **`make latex biber latex1 biber1 latex2 latex3 latex4`**
1. **`make latex biber latex1 biber1 latex2 latex3 latex4 halt=1 debug=1`**
1. **`make latex biber latex1 biber1 latex2 latex3 latex4 biber2 latex5`**
1. **`make latex biber latex1 biber1 latex2 latex3 latex4 biber2 latex5 halt=1 debug=1`**

Se você quiser saber quais são todos os comandos de compilação disponíveis,
basta chamar utilizar o comando `make help`. Exemplo:
```
$ make help

 Usage:
   make <target> [debug=1]

 Use debug=1 to run make in debug mode. Use this if something does not work!
 Examples:
   make help
   make debug=1
   make latex debug=1
   make thesis debug=1

 If you are using Windows Command Prompt `cmd.exe`, you must use the
 command like this:
  make help
  set "debug=1" && make
  set "debug=1" && make latex
  set "debug=1" && make thesis

 Use halt=1 to stop running on errors instead of continuing the compilation!
 Also, use debug=1 to halt on errors and fix the errors dynamically.

 Examples (Linux):
   make halt=1
   make latex halt=1
   make thesis halt=1

   make debug=1 halt=1
   make latex debug=1 halt=1
   make thesis debug=1 halt=1

 Examples (Windows):
   set "halt=1" && make halt=1
   set "halt=1" && make latex halt=1
   set "halt=1" && make thesis halt=1

   set "debug=1" && "halt=1" && make halt=1
   set "debug=1" && "halt=1" && make latex halt=1
   set "debug=1" && "halt=1" && make thesis halt=1

 Targets:
   all        Call the `thesis` make rule
   index      Build the main file with index pass
   biber      Build the main file with bibliography pass
   latex      Build the main file with no bibliography pass
   pdflatex   The same as latex rule, i.e., an alias for it
   latexmk    Build the main file with pdflatex biber pdflatex pdflatex
              pdflatex makeindex biber pdflatex

   thesis     Completely build the main file with minimum output logs
   verbose    Completely build the main file with maximum output logs
   clean      Remove all cache directories and generated pdf files
   veryclean  Same as `clean`, but searches for all generated files outside
              the cache directories.

   release version=1.1
       creates the zip file `1.1.zip` on the root of this project,
       within all latex required files. This is useful to share or
       public your thesis source files with others. If you are using
       Windows Command Prompt `cmd.exe`, you must use this command like this:
       set "version=1.1" && make release

   remote     Runs the make command remotely on another machine by ssh.
              This requires `passh` program installed. You can download it from:
              https://github.com/clarkwang/passh

       You can define the following parameters:
       4. args - arguments to pass to the rsync program, see 'rsync --help'
       3. rules - the rules/arguments to pass to the remote invocation of make
       5. UFSCTHESISX_ROOT_DIRECTORY  - the directory to put the files, defaults to '~/LatexBuild'
       1. UFSCTHESISX_REMOTE_PASSWORD - the remote machine SHH password, defaults to 'admin123'
       2. UFSCTHESISX_REMOTE_ADDRESS  - the remote machine 'user@ipaddress', defaults to 'linux@192.168.0.222'

     Example usage for Linux:
       make remote rules="latex debug=1" &&
              debug=1 &&
              args="--delete"
              UFSCTHESISX_ROOT_DIRECTORY=~/Downloads/Thesis &&
              UFSCTHESISX_REMOTE_ADDRESS=linux@192.168.0.222 &&
              UFSCTHESISX_REMOTE_PASSWORD=123 &&

     Example usage for Windows:
       set "rules=latex debug=1" &&
              set "debug=1" &&
              set "args=--delete" &&
              set "UFSCTHESISX_ROOT_DIRECTORY=~/Downloads/Thesis" &&
              set "UFSCTHESISX_REMOTE_ADDRESS=linux@192.168.0.222" &&
              set "UFSCTHESISX_REMOTE_PASSWORD=123" &&
              make remote
```

Caso você tenha problemas,
error ou algo não funcione,
execute o make file em modo debug.
Para isso,
basta chamar ele como você normalmente faz,
mas passando o parâmetro `debug=true`.
Por exemplo,
`make latex debug=true`.

Por conveniência,
você também pode chamar `make latex debug=a` qualquer outra coisa desde que não seja vazio.
Por exemplo,
`make latex debug=1` Você também pode diretamente editar o arquivo `setup/makefile.mk` e
descomentar a linha `# ENABLE_DEBUG_MODE := true` para ativar o modo debug permanentemente.


##  Normas da UFSC para trabalhos acadêmicos

Na UFSC,
a Biblioteca Central disponibiliza um site específico para as normas e foi com base nessas informações que este projeto foi feito.
1. [Geral](http://portal.bu.ufsc.br/normalizacao/)
1. [Normas de Citação](http://www.bu.ufsc.br/design/Citacao1.htm)
1. [Normas em docx](http://www.bu.ufsc.br/design/TemplateTrabalhoAcademico.docx)
1. [Capa](http://www.bu.ufsc.br/design/Guia_Rapido_Diagramacao_Trabalhos_Academicos.pdf)
1. [Dados da ficha](http://ficha.bu.ufsc.br/)
1. [Ficha de identificação da obra](http://portal.bu.ufsc.br/servicos/ficha-de-identificacao-da-obra/)


## Site da abnTeX2

1. [abnTeX2](http://www.abntex.net.br/)
1. https://github.com/abntex/abntex2
1. https://github.com/abntex/biblatex-abnt


# Mudanças

Para ver as mudanças, acesse o histórico do `git` no endereço:
1. https://github.com/ufsc/ufscthesisx/commits/master

Ou clone este repositório e execute seguinte comando do cliente git:
```bash
git log
```
1. https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History


# Licença

```
Copyright (c) 2012-2014 by abnTeX2 group at http://abntex2.googlecode.com/
Copyright (c) 2014-2015 Mateus Dubiela Oliveira
Copyright (c) 2015-2016 Adriano Ruseler
Copyright (c) 2017-2018 Evandro Coan, Luiz Rafael dos Santos

É concedida permissão, gratuitamente, a qualquer pessoa que obtenha uma cópia deste modelo e
software e arquivos de documentação associados (o "Software"), para ter estes arquivos com os
direitos de uso, cópia, modificação, mesclagem, publicar, distribuir, e permitir que as pessoas a
quem o Software seja fornecido tenham estes mesmos direitos, ambos sujeitos às seguintes condições:

O aviso de direitos autorais acima e este aviso de permissão devem ser incluídos em todas as cópias
ou partes substanciais do Software.

Os arquivos `chapters/intro.tex`, `chapters/chapter_1.tex` e `setup/ufscthesisx.sty` estão
licenciados sobre a licença LPPL (The Latex Project License). Portanto você deve respeitar essa
licença para esses arquivos ao invés dessa. Entretanto a condição a seguir continuará valendo sobre
esses arquivos licenciados pela licença LPPL:

OS ARQUIVOS NESTE REPOSITÓRIO SÃO FORNECIDOS "NO ESTADO EM QUE SE ENCONTRAM", SEM GARANTIA DE
QUALQUER TIPO, EXPRESSA OU IMPLÍCITA, INCLUINDO, MAS NÃO SE LIMITANDO ÀS GARANTIAS DE
COMERCIALIZAÇÃO, APTIDÃO PARA UM PROPÓSITO ESPECÍFICO E NÃO INFRACÇÃO. EM NENHUMA CIRCUNSTÂNCIA, OS
AUTORES OU TITULARES DE DIREITOS AUTORAIS SERÃO RESPONSÁVEIS POR QUALQUER RECLAMAÇÃO, DANOS OU OUTRA
RESPONSABILIDADE, SEJA EM AÇÃO DE CONTRATO, DELITO OU DE OUTRA FORMA, DECORRENTE, DESTE OU
RELACIONADO COM DOS ARQUIVOS DESTE REPOSITÓRIO OU O USO OU OUTRAS NEGOCIAÇÕES NO MODELO E SOFTWARE.
```


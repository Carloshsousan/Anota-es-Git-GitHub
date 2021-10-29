# Introdução ao Git e ao Github
**O software é feito de forma colaborativa, você não faz nada sozinho.**

Navegação via Command Line interface e instalação



**COMANDOS BÁSICOS PARA UM BOM DESEMPENHO NO TERMINAL Windows:**

- cd (possibilita a navegação entre as pastas)

- dir (listar diretórios/pastas no pc)

- mkdir (criar uma pasta).. ( dois pontos retrocede)

- cls (limpar o terminal)

- tecla Tab (alto-completa)

- “>” (redirecionador de fluxo) pega o output da função echo e joga dentro de um arquivo.del (comando para deletar apenas arquivos dentro de uma pasta)

- Seta para cima (histórico dos comandos executados)

- rmdir + repositório + /S + /Q ( excluir o repositório)

  

  **Unix:**

  

  - cd (possibilita a navegação entre as pastas)

  - ls (listar diretórios/pastas no pc)mkdir (criar uma pasta)

  - rm-rf ( excluir o repositório).. ( dois pontos retrocede)

  - clear ou ctrl + L (limpar o terminal)

  - “>” (redirecionador de fluxo) pega o output da função echo e joga dentro de um arquivo.

    

**TÓPICOS FUNDAMENTAIS PARA ENTENDER O FUNCIONAMENTO DO Git**

SHA1 (Secure Hash Algorithm) = conjunto de funções hash criptográficas projetadas pela NSA (Agência de Segurança Nacional dos EUA).
Gera um conjunto de caracteres identificador de 40 dígitos.



Comando dentro do Git:
$ openssl sha1 (arquivo que está sendo alterado)



OBJETOS INTERNOS DO Git
Blobs: contém metadados do Git que são o tipo do objeto, tamanho da string, tamanho do arquivo, entre outros. 



Tree: armazena blobs, guarda o nome do arquivo e o sha1. É responsável por montar toda a estrutura de onde estão localizados os arquivos. Apontam para árvores e para blobs.
![img](https://lh3.googleusercontent.com/FXHUi1BhiDGIWHj6sHIGLkevQ8oP95jNB9dnsps8vA4zdg9Y0RoO-ut62rkHv8rOh_n1zr1bM_JcqJQSjP9KpmwUT7Iz7AeG5WFEfEzEpOC3O5sy0qK-rsiYNX3MgHe26rBIo7qL)



Commit: Aponta para uma tree, para outro commit, para o autor, e para uma mensagem. Possuem um sha1 dos seus metadados. 
![img](https://lh3.googleusercontent.com/8uokUTY8tB616-utMdzNG4WlZu0sLxwHkcSCrGD3VUBEG87dqxwJPEn0RHgG0o8H0yO02jQQlfICpokPEy97K-W_OVWGLj18vQqDoYc-1Pck7EWFvGyb943T574P_L_h2s7k-9fD)



**CHAVE SSH E Token**

Chave SSH: Três passos para colocar essa senha na máquina e no GithubBaixar o repositório via ssh.

Token: Senha gerada no próprio GithubBaixar o repositório via https 

### Primeiros Comandos com Git

**INICIANDO O Git e CRIANDO UM COMMIT**

Comandos:

Git init: inicia o Git 

-a = pastas ocultas

**Configurações iniciais do Git:**

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ git config --global user.email "xx@gmail.com"

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ git config -- user.name Perkles

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ git add *

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ git commit -m "commit inicial"[master (root-commit) 65320f7] commit inicial 1 file changed, 0 insertions(+), 0 deletions(-) create mode 100644 strogonoff.md


_Usar a extensão .md (markdown) para trabalhar de forma humanizada o html no typora._

_No typora, ir em ajudas e ler a documentação._

### Ciclo de vida dos arquivos no Git

**PASSO A PASSO NO CICLO DE VIDA**

Trabalhando dentro do Git: "Comandos"

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ lsstrogonoff.md

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ git statusOn branch masternothing to commit, working tree clean

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ mkdir receitas

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ lsreceitas/ strogonoff.md

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ mv strogonoff.mdmv: missing destination file operand after 'strogonoff.md'Try 'mv --help' for more information.

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ mv strogonoff.md ./receitas/

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ git statusOn branch masterChanges not staged for commit: (use "git add/rm <file>..." to update what will be committed) (use "git restore <file>..." to discard changes in working directory)    deleted:  strogonoff.md
Untracked files: (use "git add <file>..." to include in what will be committed)    receitas/
no changes added to commit (use "git add" and/or "git commit -a")

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ git add strogonoff.md receitas/

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ git statusOn branch masterChanges to be committed: (use "git restore --staged <file>..." to unstage)    renamed:  strogonoff.md -> receitas/strogonoff.md

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ git commit -m "criar pasta receitas, move arquivo para receitas"[master ab17ffa] criar pasta receitas, move arquivo para receitas 1 file changed, 0 insertions(+), 0 deletions(-) rename strogonoff.md => receitas/strogonoff.md (100%)

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ git statusOn branch masternothing to commit, working tree clean

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ lsreceitas/

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ echo > README.md

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ lsREADME.md receitas/

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ git statusOn branch masterUntracked files: (use "git add <file>..." to include in what will be committed)    README.md
nothing added to commit but untracked files present (use "git add" to track)

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ git add *warning: LF will be replaced by CRLF in README.md.The file will have its original line endings in your working directory

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ git statusOn branch masterChanges to be committed: (use "git restore --staged <file>..." to unstage)    new file:  README.md

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ git commit -m "adiciona index"[master 5b40557] adiciona index 1 file changed, 6 insertions(+) create mode 100644 README.md



### Introdução ao GitHub

**TRABALHANDO COM O GitHub**

Comandos: git config --global --unset user (deletar uma propriedade dentro do git)

git config --list (obter as informações do git no pc)

**Adicionando repositório no Github**

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ git remote add origin https://github.com/Carloshsousan/livro-receitas.git

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ git remote -vorigin https://github.com/Carloshsousan/livro-receitas.git (fetch)origin https://github.com/Carloshsousan/livro-receitas.git (push)

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ git statusOn branch masternothing to commit, working tree clean

carlo@DESKTOP-CCVPT5A MINGW64 /c/workspace/livro-receitas (master)$ git push origin master

Enumerating objects: 8, done.Counting objects: 100% (8/8), done.Delta compression using up to 4 threadsCompressing objects: 100% (5/5), done.Writing objects: 100% (8/8), 774 bytes | 154.00 KiB/s, done.Total 8 (delta 0), reused 0 (delta 0), pack-reused 0To https://github.com/Carloshsousan/livro-receitas.git * [new branch]   master -> master

### Resolvendo Conflitos

**COMO OS CONFLITOS ACONTECEM NO GitHub E COMO RESOLVÊ-LOS**

_Obs! SEMPRE que houver modificações no arquivo é necessário ver o status do git, adicionar esta modificação, fazer o commit, e assim fazer o push deste repositório._

Para solucionar conflitos utilizamos o comando: 

$ git pull (repositório)
E resolva as alterações manualmente. 


Depois faça o push novamente.


Comando para clonar:
$ git clone (link repositório)
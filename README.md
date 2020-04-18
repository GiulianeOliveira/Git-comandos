# Tutorial git para iniciante
Este repositório possui um pequeno tutorial explicando o que é o git, como configurá-lo, como inicializar um
repositório e alguns comandos essenciais.

## O que é o git? :octocat:
-> É um sistema de controle de versão. O git trabalha com versionamento de arquivos, através de seus estados, chamados de snapshots.

## Instalando o git no linux:
-> Baixe o programa diretamente no site: https://git-scm.com/downloads
-> Caso utilize uma distro linux baseada em Debian/Ubuntu você pode utilizar o comando $ sudo apt-get install git para baixar e instalar o git diretamente do seu terminal.

## Desinstalando o git:
-> Em distros baseadas em Debian/Ubuntu utilize diretamente no seu terminal comando $ sudo apt-get purge git para remover tudo, até os arquivos de configuração ou utilize o comando $ sudo apt-get remove git para manter apenas os arquivos de configuração e remover o restante.

## Atualizando o git:
-> Antes de atualizá-lo verifique a versão que está instalada na sua máquina com o comando git --version, a versão mais recente atualmente (08/04/2020) é a 2.26.0
Em seguida, abra o terminal e digite:
    $ sudo add-apt-repository ppa:git-core/ppa
    $ sudo apt-get update
    $ sudo apt-get install git

## Iniciando o git na sua máquina:
-> Após ter baixado e instalado o git na sua máquina, você deve configurar o seu git. 

    Para definir seu nome de usuário, abra o terminal e digite:
        $ git config --global user.name "Fulano da Silva"
    
    Para definir o seu e-mail:
        $ git config --global user.email "Fulano@hotmail.com"
    
    Para definir o seu editor de texto principal do git:
        $ git config --global core.editor "vscode"
    
## Inicializando um repositório:
-> Crie uma pasta no diretório desejado:
    $ mkdir "Nome-da-pasta"
-> Acesse a pasta:
    $ cd Nome-da-pasta
-> Em seguida inicialize o repositório:
    $ git init

## Alguns comandos importantes:
#####   **Verificar a versão do git instalado na sua máquina:** 
    $ git --version

#### **Mostrar o estado atual do seu repositório:**
    $ git status

###### Adicionar arquivos no git:
$ git add arquivo
**Obs: todos os arquivos adicionados no git devem ser commitados, ou seja, será criada uma imagem(snapshot), uma versão desses arquivos.

Fazer um commit:
$ git commit -m "Informe sua mensagem aqui"
**Obs: a cada modificação feita em um arquivo já comitado, o mesmo deve ser adicionado ao git e comitado novamente. 

Fazer push para o repositório remoto, atualizando-o conforme o seu repositório local:
$ git push -u origin master

Visualizar todos os autores e os comentários do que cada um comitou no repositório:
$ git shortlog 

Visualizar o que foi adicionado na versão da Hash escolhida:
$ git show nome_da_hash

Visualizar o que foi adicionado ao arquivo ainda não adicionado:
$ git diff 

Visualizar todos os commits realizados e suas hashes:
$ git log

Clonar um repositório já existente:
$ git clone url_do_repositório

## O que fazer quando fiz um commit que não deveria?
-> Você deve retornar ao commit anterior, ou seja, a versão anterior ao seu commit "errado". Para isso, no diretório do repositório local digite o comando:
    $ git log
Selecione a penúltima hash (ou a hash que deseja retornar) e copie-a. Em seguida, você deve escolher entre um destes três comandos para retornar ao commit no qual você selecionou a hash:

    1 - o soft "cancela" o seu commit errado e retorna deixando os arquivos prontos para serem commitados novamente:
    $ git reset --soft cole_aqui_a_hash

    2 - o mixed, "cancela" o seu commmit errado e retorna deixando os seus arquivos como modified, ou seja, o mesmo pode ser editado, adicionado e commitado novamente:
    $ git reset --mixed cole_aqui_a_hash

    3 - o hard, ignora a existência do commit errado, tudo que foi feito nele é descartado. Retorna para o commit selecionado.
    $ git reset --hard cole_aqui_a_hash

## Como faço para apagar as mudanças de um arquivo que ainda não adicionei em um repositório?
    Este comando descarta as mudanças no diretório local de trabalho:
    $ git checkout nome_do_arquivo

## E para apagar as mudanças de um arquivo já adicionado, mas que ainda não commitei?
    Você deve utilizar este comando, ele retira o arquivo selecionado da lista dos arquivos prontos para commitar:
    $ git reset HEAD nome_do_arquivo
    E em seguida, utilize:
    $ git checkout nome_do_arquivo
    para apagar as mudanças no diretório local de trabalho.

## Criando uma chave SSH:
    O SSH é um protocolo que serve para autenticar um usuário remoto à um servidor. Para saber mais você deve acessar:
    https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh

## Ligando um repositório local a um remoto:
    No terminal, dentro do diretório local do repositório digite:
        $ git remote add origin url_do_repositório_remoto
    No meu caso, por exemplo:
        $ git remote add origin https://github.com/GiulianeOliveira/Git-comandos.git

    DICA: utilize $ git remote -v para mais informações sobre o repositório.

    Em seguida, utilize o comando:
        $ git push -u origin master 
    para enviar os arquivos para o repositório remoto.

## O que é fork de um projeto:
    É um projeto que não é seu, é realizada uma cópia do mesmo para que você possa contribuir. Assim que
    feitas as suas contribuições, você realiza um pull request para enviar ao dono do repositório os arquivos
    com as suas modificações.



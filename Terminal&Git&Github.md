# Terminal & Git & Github 🧭

## Comandos úteis no terminal 🧑‍💻

1. Navegar entre as pastas

Linux

```bash
cd
```
Windows
```bash
cd
```

1. Voltar uma pasta 

Linux

```bash
cd ../
```
Windows
```bash
cd ..
```

1. Listar as pastas

Linux

```bash
ls
```
Windows

```bash
dir
```

1. Criar pastas

Linux

```bash
mkdir nome_da_pasta
```
Windows

```bash
mkdir nome_da_pasta
```

1. Criar arquivos

Linux

```bash
echo hello > hello.txt
```
Windows
```bash
echo hello > hello.txt
```

1. Deletar pastas/arquivos

Linux

```bash
rm -rf
```
Windows
```bash
rmdir nome_do_arquivo /s /q
```

Obs: temos no Windows a opção del, porem ela somente apaga o conteúdo da pasta não a pasta em si.

1. limpar dados no terminal

Linux

```bash
clear
```
Windows
```bash
cls
```

Obs: no linux temos a opção de segurar a tecla ctrl + l para limpar as informações exibidas no terminal.

## Git Download for Linux and Unix 💻

Passo a passo para instalar o git com sua versão mais recente do git, e colocando sim para tudo.

Passo 1:

```bash
sudo add-apt-repository ppa:git-core/ppa -y
```

Passo 2

```bash
sudo apt update
```

Passo 3

```bash
sudo apt install git
```

Passo 4 checando a versão do git

```bash
git --version
```

## Comandos úteis no git 👨‍💻

Antes de tudo temos que ir até a pasta a qual queremos iniciar o git no terminal, então já na pasta podemos usar os seguintes comandos:

1. Inicializar o git no repositório

```bash
git init 
```

1. Para verificar se foi iniciado corretamente basta colocar o seguinte comando para poder vizualizar-lo:

```bash
ls -a
```
### Configurar o git

1. Para configurar o git usamos os seguintes códigos:

```bash
git config --global user.email "seu_email@email.com"
```

Obs: Use o seu e-mail do github

1. Para configurar o nome de usário basta colocar o seguinte código:

```bash
git config --global user.name seu_nome_de_usuario
```

Obs: Use o seu nome de usuário do github, para facilitar a integração do git e github posterioremente.

1. Para adicionar um novo arquivo monitorado pelo git basta usar o seguinte código:

```bash
git add nome_do_arquivo
git add *
git add .
```

Obs: para um único arquivo usaremos a primeira linha de código, já para multiplos arquivos usaremos a segunda linha ou a terceira linha de código.

1. Para commitar um arquivo basta colocar a seguinte linha de código:

```bash
git commit -m "commit inicial"
```

Obs: Você pode colocar qualquer mensagem entre essas aspas duplas que sejam relacionadas as alterações que vocẽ fez no decorrer do seu projeto, para um commit inicial pefiro deixar como está na linha de código acima.

1. Para visualizar o status do monitoramento do seu arquivo basta colocar o seguinte comando:

 

```bash
git status
```

### Conectando o Git ao Github

Passo a passo:

1. Primeiro acesse seu github
2. Crie um novo repositório
3. Com ele já criado copie o link do seu repositório
4. Para conectar o git ao github basta colocar o seguinte código:

 

```bash
git remote add origin link_copiado_do_passo_3
```

1. Para a primeira conecção é necessário usar o seguinte código:

```bash
git push origin master
```

Obs: nesse passo o git empurra seu vercionamento para o github.

1. É necessário também puxar os arquivos vercionados no github caso existam. Para a primeira vez usamos o seguinte código:

```bash
git pull origin master
```

Obs: nessa etapa ele resolve os conflitos de branchs caso existam.

## Chave SSH 🔐 Linux

Passo a passo de como ativar a chave SSH no Github.

1. Acesse seu github
2. Clique no icone que coném sua imagem e clique em Settings
3. Será carregado uma nova aba, no menu lateral esquerdo busque a opção SSH and GPG keys
4. Clique no botão verde ao lado direito onde está escrito New SSH key
5. Aparecerá  dois campos principais o Title que é o nome da máquina a qual você está querendo conectar com o github e a key onde colocaremos nossa chave pública a qual vamos obter nos passos a seguir.
6. Abra o seu terminal, dica: use um diretorio que seja fácil para localizar suas chaves.
7. Em seguida digite o seguinte código:

 

```bash
ssh-keygen -t ed25519 -C seuemail@email.com
```

1. Ele ira gerar um caminho padrão então é só clicar em enter.
2. Ele vai pedir para colocar uma senha para essa chave, então basta colocar uma senha.
3. Navegue até a pasta do caminho que foi gerado. use o comando ls para listar os arquivos dessa pasta, se o diretorio estiver correto ele terá como saída dois arquivos, um id_ed25519 e outro é id_ed25519.pub que são suas chaves, a primeira é a privada e a segunda é a pública.
4. Para mostar o conteúdo dela basta colocar o comando:

```bash
cat id_ed25519.pub
```

1. Copie o conteúdo dela e vá até o github, coloque um nome para sua máquina no campo Title, cole o conteúdo que foi copiado do arquivo id_ed25519.pub para o campo Key que falamos no passo 5. Então clique em Add SSH key
2. E aí sua chave pública foi adcionada, agora temos que passar essa chave para o agente.
3. Para passar a chave para o agente basta colocar o seguinte código:

```bash
eval $(ssh-agent -s)
```

1. Depois passe sua chave privada da seguinte forma no terminal:

```bash
ssh-add id_ed25519
```

1. Ele pedira a senha que foi criada no passo 9, coloque a senha.  
2. E por fim a identidade foi criada.

## Referências:

[https://gist.github.com/leocomelli/2545add34e4fec21ec16](https://gist.github.com/leocomelli/2545add34e4fec21ec16)

[https://linux.ime.usp.br/~lucasmmg/livecd/documentacao/documentos/terminal/Terminal_basico.html](https://linux.ime.usp.br/~lucasmmg/livecd/documentacao/documentos/terminal/Terminal_basico.html)

[https://www.alura.com.br/artigos/cmd-dicas-para-trabalhar-no-prompt-do-windows](https://www.alura.com.br/artigos/cmd-dicas-para-trabalhar-no-prompt-do-windows)

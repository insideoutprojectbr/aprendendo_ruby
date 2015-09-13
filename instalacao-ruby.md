#Instalação Ruby

##RVM (Ruby Version Manager)
Ferramenta que facilita a instalação e gerenciamento de múltiplas versões de Ruby e conjuntos de dependências de um projeto, chamadas **gems**. **Gemset** é o **conjunto de gems**.

#### Instalação
```shell
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
sudo apt-get install curl
curl -sSL https://get.rvm.io | bash -s stable --ruby #Instala o rvm, com a versão mais recente de ruby
```
Para que o RVM seja inicializado, é preciso fechar a janela do terminal, e abrir uma nova, ou executar o seguinte comando na janela de terminal corrente:
```shell
source ~/.rvm/scripts/rvm
```
#### Comandos úteis 

##### Instala um versão de ruby
```shell
rvm install versao_de_ruby
```
##### Seleciona um versão de ruby
```shell
rvm use versao_de_ruby
```
##### Seleciona versão de Ruby em determinado gemset(Cria se não existir)
```shell
rvm use versao_de_ruby@nome_do_gemset --create
```
##### Cria um gemset
```shell
rvm gemset create nome_do_gemset
```
##### Remove um gemset
```shell
rvm gemset delete nome_do_gemset
```
##### Esvazia um gemset
```shell
rvm gemset empty nome_do_gemset
```
Leia mais em: https://rvm.io

#### .ruby-version e .ruby-gemset
Com o fim de facilitar a seleção de ruby e criação de gemset próprio, no diretório do seu projeto podem ser criados os arquivos .ruby-version (responsável por escolher versão de ruby) e .ruby-gemset (responsável por escolher o gemset, caso não exista é criado automaticamente). Esses arquivos serão lidos automaticamente pelo RVM no momento em que se entre no diretório do projeto.

##### .ruby-version
```
2.2.1
```
##### .ruby-gemset
```
nome_do_gemset
```

## RubyGems

Gerenciador de pacotes de Ruby que possibilita a distribuição de programas e bibliotecas empacotadas em um formato chamado **gem**. Faz parte da biblioteca padrão de Ruby desde a versão 1.9.

####Comandos úteis

##### Instala uma gem
```shell
gem install nome_da_gem
```
##### Instala uma gem em uma versão específica
```shell
gem install nome_da_gem -v versao_da_gem
```
##### Desinstala uma gem
```shell
gem uninstall nome_da_gem
```
##### Atualiza uma gem
```shell
gem update nome_da_gem
```
Leia mais em: http://guides.rubygems.org

## Bundler

Ferramenta que facilita o gerenciamento de gems de um projeto. Todas as dependências de um projeto são definidas em um arquivo chamado Gemfile. Uma vez criado esse arquivo, as gems podem ser baixadas e instaladas automaticamente. 

Antes de instalar as gems, essa ferramenta verifica se as versões das gems definidas são compatíveis entre si e se estas podem ser todas carregadas ao mesmo tempo. Após a instalação, o arquivo Gemfile.lock é gerado, responsável por armazenar as versões exatas de gem que foram instaladas, permitindo consistência entre ambientes em que vários desenvolvedores trabalham juntos, por exemplo.

##### Instalação
```shell
  gem install bundler
```

#### Comandos úteis

##### Gera um Gemfile no diretório corrente
```shell
  bundle init
```
##### Instala as gems definidas no Gemfile
```shell
  bundle install
```
##### Remove gems não utilizadas no projeto
```shell
  bundle clean --force
```
##### Atualiza a versão da gem no Gemfile.lock
```shell
bundle update nome_da_gem
```
##### Atualiza todas as gems
```shell
bundle update
```
Leia mais em: http://bundler.io

## Versionamento Semântico
Tanto as versões de Ruby, como as de suas gems seguem o versionamento semântico.

Leia mais em: http://semver.org/lang/pt-BR/

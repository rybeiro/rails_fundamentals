# RAILS
## criar uma aplicação
```ruby
# criar um app com versão mais atual do rails
rails new nome_app

# criar um app com versão especifica
rails _5.2_ new nome_app

# Indicando o banco de dados do app
rails new nome_app --database=mysql
```

## MVC
É um padrão de projeto, (M) model, (V) view e (C) controller

(M) Model deve ser escrito no singular. exemplo, nome do arquivo: coin.rb nome da Classe Coin.

(V) View é organizado em diretorios. exeemplo, diretorio coins contém todos os arquivos html e outros.

(C) Controller deve ser escrito no plural. exemplo, nome do arquivo coins_controller.rb nome da Classe CoinsController


## CRUD
```ruby
# Scaffold é um generator do rails para gera o crud
rails generate scaffold  model:nome_tabela field:dat_type ... field:data_type
# O rails tem outros generators

```

## Console
### dbconsole
Para acessar o database através de um app rails utiliza-se o comando _rails dbconsole_
```ruby
rails dbconsole # ou rails db
```

### tasks
São tarefas pré-definidas para execução
```ruby
# lista de todas as tasks disponíveis
rails -T

# fitrar por um grupo específico
# exemplo filtrando todas as tasks para database
rails -T db
```

#### database
```ruby
# criando um database
rails db:create
# excluindo um database
rails db:drop
# executando migrations
rails db:migrate
# desfazendo a ultima migrations
rails db:rollback
```

## Server (servidor)
Para subir o servidor utilizar o comando
```ruby
# por padrão o servidor é iniciado em desenvolvimento
rails s

# para iniciar o servidor em produção
rails s RAILS_ENV=production # ou rails s -e production
```

## Geradores (generators)
```ruby
# lista de generators
rails generator # ( Enter ) ou
rails g # ( Enter )

# é possível gerar Models e Controller
rails g model:name_class field:data_type field:data_type # field:string field:integer ...

#criar controller
rails g controller name_class

# Ao criar um controller com as views
rails g controller name_class name_action name_action # name_action=index name_action=edit ...
rails g controller welcome index 

# Para remover um controller
rails g controller name_class 
```

## Helpers
_Helpers_ são métodos prontos que são usados nas _views_

Os _helpers_ estão disponíveis no diretório _app/helpers_ e no arquivo application_helpers.rb todo conteúdo fica disponível para todas as view do app. Mas você também pode criar seus próprios helper dentro desse diretório. E para organização criar com o nome da view.


```ruby
# link_to
<%= link_to "Cadastro de Moedas", coins_path %>
```

```ruby
<%= image_tag coin.url_image, size: "25x25" %>

```

## Seed
É possível popular a tabela criando os dados através de _seed_
```ruby
# bd/seed.rb
# contém instruções para criar as seeds
```

## Cookies
Cookies são armazenados no navegador
```ruby
# criando um cookies
cookies[:nome]
``` 

## Session
Session são armazenadas no servidor
```ruby
# criando a session
session[:nome]
```

## Map
```ruby
[1,2,3,4,5].map do |i|
	i*3
end

[1,2,3,4,5].map{|i| i*5}

c = Contact.all
c.map(&:first_name)

# gerando um novo array
c.map{|i| [i.first_name, i.cpf]}
```

## Pluck
c.pluck(:first_name, :cpf)

# Primeiro app
## Agenda de contatos
Vou criar uma api de agenda de contatos
```ruby
# criando o app
rails new app_contacts --api --databases=mysql

# depois acesse o arquivo config/database.yml
# configure o usuário e senha do banco de dados

# Criar o banco de dados
rails db:create

# Subir o servidor puma
rails server
```

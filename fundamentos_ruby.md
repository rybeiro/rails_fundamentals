# ARRAY
```ruby
#sintaxe e uso
# Criar um array
arr = Array.new # ou arr = []

# incluir elementos
arr.push(1)
arr.push("teste")
arr.push([1,2,3])

# acessar um elemento
arr[0]
arr[1]
arr[2]

# percorrer cada elemento
arr.each do | item |
	puts item
end
```

# HASH
```ruby
# Hash é uma lista com chave/valor, onde nós definimos a chave
# sintaxe e uso
# criar um hash
h = Hash.new # ou h = {}

# incluir chave/valor

h["teste"] = 123

# acessar o elemento
h["teste"]

# percorrer cada elemento


```

# STRING -> CONCATENAÇÃO
```ruby
# concatenação utlizando o sinal de (+). Evitar de utiliza-lo para concatenar 
# porque cria uma nova posição de mémoria.
# para determinar a posição do objeto em mémoria
# utilize objetct_id
a = "Curso"
b = "Rails"
a.object_id
b.object_id
a = a + b
a.object_id
b.object_id

# concatenação utilizando a pá (<<). Uso recomendado porque mantém a mesma posição na mémoria.
i = "Curso"
j = "Rails"
i.object_id
j.object_id
i = i << j
i.object_id
j.object_id

```

# STRING -> INTERPOLAÇÃO
```ruby
nome = "Nome"
sobrenome = "Sobrenome"

puts "Seu nome #{nome} de #{sobrenome}"
```

# SYMBOL ( SÍMBOLOS )
```ruby
# sintaxe
# para criar um símbolo incluir (:) na frente da string. ex: :nome
# São strings imutáveis. Quando utilizadas ela mantém a mesma referência na mémoria

# observe que a mesma string cria novas posições na mémoria
puts "Novo".object_id
puts "Novo".object_id
puts "Novo".object_id
puts "Novo".object_id

# observe que agora permanece o mesmo
puts :nome.object_id
puts :nome.object_id
puts :nome.object_id
puts :nome.object_id
```


# Classes
A classe pode ser imaginada como uma forma ou projeto ou receita.

# Objeto
O objeto pode ser imaginado como o produto oriundo da forma ou projeto ou receita.

# Métodos
São ações

# Atributos ou propriedades
São características

## identificando um objeto
Para identificar um objeto podemos utilizar o método _object_id_
```ruby
"Este objeto está no alocado no seguinte ponto de mémoria".object_id
```

## Identificar o tipo de dado
Para identificar o tipo de dado de podemos utilizar o método _class_
```ruby
"Eu pertenço ao tipo de dado".class
```

# Criando classe, objeto, métodos e atributos
```ruby
# Classe devem ter criado em CamelCase.
class PessoaFisica
  # Método
  def falar
    puts "Olá mundo!"
  end
end

# Objeto
p = PessoaFisica.new

# usando o método
p.falar
```

# Método initializer ( construtor )
```ruby
class Pessoa
  def initialize
    puts "sempre será executado quando a classe for instanciada"
  end

individuo = Pessoa.new
```

# Self
é o próprio objeto instânciado
```ruby
class Pessoa
   def initialize
     puts "Eu sou uma classe"
   end

   def my_id
     puts self.object_id
   end
end

p = Pessoa.new
p.my_id

```

# Variáveis de instância
Variáveis de instância são precedidas de @ e só existe na instãncia em que foi criada.

# Accessor
São atalhos para declaração de atributos, facilitam o acesso e a atribuição de valors. Semelhantes ao Get e Set de algumas linguaguens.

```ruby
# sintaxe: attr_accessor
class Pessoa
  attr_accessor :nome
end

p = Pessoa.new
p.nome = "José"
puts p.nome
```

# Classes e Heranças


# Módulos ou Mixins
Em um módulo podemos ter constantes, métodos ou classes. Pense em utiliza-los quando precisar de multipla herança.
```ruby
# pagamento.rb
module Pagamento
  PI = 3.14

  def teste
    "Isso é apenas um método em um módulo"
  end

  class Pessoa
    def saudacao
      "Seja bem vindo"
    end
  end
end

# outro_arquivo.rb
# utilizando os módulos
require_relative 'pagamento'
include Pagamento

puts Pagamento::PI

puts Pagamento::teste

p = Pagamento::Pessoa.new
puts p.saudacao
```

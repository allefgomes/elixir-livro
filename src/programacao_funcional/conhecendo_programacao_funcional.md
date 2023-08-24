# Conhecendo Programação Funcional

A [Programação Funcional (FP)](https://pt.wikipedia.org/wiki/Programa%C3%A7%C3%A3o_funcional) é um paradigma de programação que trata a computação como uma avaliação de funções matemáticas e que evita estados ou dados mutáveis.

Ou seja, a FP promove a imutabilidade, a ausência de efeitos colaterais e a expressão de lógica por meio de funções. Não é algo novo, é o segundo paradigma de programação criado, porém atualmente temos uma crescida de linguagens de programação que se baseiam na FP porque resolve alguns problemas que temos quando trabalhamos com [Orientação a Objetos (OOP)](https://pt.wikipedia.org/wiki/Programa%C3%A7%C3%A3o_orientada_a_objetos).

Neste capítulo iremos entender pilares da programação funcional.

## Funções como Cidadãos de Primeira Classe (First Class Citizens)
Funções como Cidadãos de Primeira Classe é um conceito em que tratamos funções da mesma maneira que tratamos outros tipos de dados, como números, strings e objetos... Na prática, conseguimos alocar uma função em uma variável e utilizá-la depois. Abaixo, temos um exemplo já em elixir que demonstra como fazer (Não se preocupe tanto com a sintática nesse momento).

```elixir
iex(1)> minha_funcao = fn (nome) -> "Olá, #{nome}!" end
#Function<42.3316493/1 in :erl_eval.expr/6>

iex(2)> minha_funcao.("João")
"Olá, João!"
```

Perceba que no `iex(1)` declaramos uma função anônima que recebe um nome e retorna um `Olá, ` e o nome recebido. Nesta, dizemos para o sistema alocar essa função em uma variável chamada `minha_funcao`.
No `iex(2)` estamos chamado a `minha_funcao` e passando o nome `João` como argumento para que ele retorne `Olá, João!`.

Dessa forma, de manipular uma função como manipulamos outros tipos de dados, chama-se `Funções como Cidadãos de Primeira Classe`.

## Imutabilidade (Immutability)

Imutabilidade é uma parte essencial da programação funcional, talvez o mais importante, ao meu ver. Como o nome já diz, imutabilidade é algo que não muda, não é alterável. Vejamos o seguinte exemplo:

```elixir
iex(1)> person = %{ name: "Maria" }
%{name: "Maria"}

iex(2)> Map.put(person, :profissao, "Programadora")
%{name: "Maria", profissao: "Programadora"}

iex(3)> person
%{name: "Maria"}
```

Note que no exemplo acima, no `iex(1)` instanciamos uma variável chamada `person` que contém um `map` - entenderemos melhor futuramente - com o `name` da pessoa. No 
`iex(2)`, informamos para o sistema adicionar o campo `profissao` com o valor `"Programadora"` no map da variável `person`. Se não houvesse imutabilidade, o valor de person seria `%{name: "Maria", profissao: "Programadora"}`, mas por conta da imutabilidade, quando chamamos a variável `person` no `iex(3)`, vemos que o retorno é apenas `%{name: "Maria"}`.

Temos muitos benefícios ao usar imutabilidade, e queria mostrar os 3 que acho principais que são:

* Termos uma maior previsibilidade e simplicidade com os dados que estamos tratando, o que faz o comportamento do sistema ser mais previsível, pois o valor não será alterado, facilitanto a lógica do programa e a compreensão do código.

* Evita efeitos colaterais não intencionais. Por exemplo, modificar acidentalmente um estado de outra parte do programa, evitando assim, bugs complexos.

* Facilita testes pois com os dados imutáveis, o comportamento é isolado e previsível.

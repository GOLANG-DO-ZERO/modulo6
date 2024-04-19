# Boas práticas de programação + "go way" - módulo 6

Começar a pensar nos "detalhes"... boas práticas de fazer as coisas. Padronizar a forma como codamos em Go


## Convenção de nomenclatura. Qual "case" usar em Go?

Existem quatro tipos que são mais comuns de convenções de nomenclatura: Camel case, Pascal case, Snake case e Kebab Case.

#### Camel case
Camel case deve começar com a primeira letra minúscula e a primeira letra de cada nova palavra subsequente maiúscula:

```
stephCardoso
golangDoZero
```

#### Pascal case
Conhecido também como “upper camel case” ou “capital case”, pascal case combina palavras colocando todas com a primeira letra maiúscula:

```
StephCardoso
GolangDoZero
```

#### Snake case
Também conhecido como “underscore case”, utilizamos underline no lugar do espaço para separar as palavras. Quando o snake case está em caixa alta, ele é chamado de “screaming snake case”:

```
steph_cardoso
GOLANG_DO_ZERO
```

#### Kebab case
Utiliza o traço para combinar as palavras. Quando o kebab case está em caixa alta, ele é chamado de “screaming kebab case”:

```
steph-cardoso
GOLANG-DO-ZERO
```

**Na linguagem Go, você deve utilizar duas delas: o Camel case e o Pascal Case**. E isso nada mais é do que uma forma de você padronizar a forma como cria variáveis, constantes, funções...

### Camel case e Pascal case no Go

- Pascal case: para exportar, ou seja, essa var/const/func poder ser utilizada fora do pacote.
- Camel case: para var/const/funcs exclusivas do pacote. Ou seja: só pode ser usada dentro do pacote que foi criada.

Exemplo:
```
package escola

type Aluno struct {
  Nome string
  Email string
  Notas []int
}

type professor struct {
  nome string
  email string
  materias []string
}

func Notas() []int {
  return []int{10, 9, 8, 10}
}
```

Nesse exemplo, a struct `Aluno` (e também os campos da struct) e a função `Notas()` poderá ser usada fora do pacote `escola`, pois começam com letra maiúscula. Já a struct `professor` é exclusiva para ser usada e acessada no pacote `escola`, já que começa com a letra minúscula.


## Escolha bons nomes

Escolher bons nomes para variáveis, funções e constantes é essencial para você ter um código limpo e de fácil leitura.

Exemplo:

```
x := []string{banana, maça, uva, kiwi}

frutas := []string{banana, maça, uva, kiwi}
```

Qual dos dois nomes (x ou frutas) deixa mais claro o conteúdo daquela variável? Claro que o nome `frutas`. Por isso, quando for escolher o nome de uma variável, constante ou função, pare e reflita: o que essa var guarda? o que essa função faz? E use essas respostas para dar um nome descritivo.

#### Evitar repetir o nome do pacote na função/variável

Se o nome do seu pacote é `log`, por exemplo, você não precisa criar uma func que também tenha esse termo `log`. Pois quando você chamar essa função, variável ou constante fora do pacote, acaba ficando repetitivo.

Exemplo:
- log.Info() // :+1:
- log.LogInfo() // :-1:

#### Índices
Em índices, procure ser curto. Utilize apenas uma letra:

Exemplo:
```
for i:= 0; i < 10; i++ {}
```

#### Nomear pacotes
Prefira **nomes curtos**. O nome deve ser claro e definir a função daquele pacote.


## Layout de organização de projetos
Instrução da própria linguagem de como organizar as pastas dos projetos: https://go.dev/doc/modules/layout

Vamos olhar isso com mais calma quando estivermos fazendo o projeto e as resoluções de desafios técnicos.


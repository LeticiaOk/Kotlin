# Kotlin

## Olá, mundo!

```Kotlin
fun main() {
    println("Hello, world!")
    // Hello, world!
}
```

- `fun` é usado para declarar uma função

- A `main()` função é onde seu programa começa

- O corpo de uma função é escrito entre chaves `{}`

- `println()` e `print()` as funções imprimem seus argumentos na saída padrão

## Variáveis

- Variáveis ​​somente leitura com `val`

- Variáveis ​​mutáveis ​​com `var`

> Não é possível alterar uma variável somente leitura depois de ter atribuído um valor a ela.

```Kotlin
fun main() { 
    val popcorn = 5    // There are 5 boxes of popcorn
    val hotdog = 7     // There are 7 hotdogs
    var customers = 10 // There are 10 customers in the queue

    // Some customers leave the queue
    customers = 8
    println(customers)
    // 8
}
```

> Variáveis ​​podem ser declaradas fora da main() função no começo do seu programa. Variáveis ​​declaradas dessa forma são ditas declaradas no nível superior .

- Como customers é uma variável mutável, seu valor pode ser reatribuído após a declaração.

> 💚 Recomendamos que você declare todas as variáveis ​​como somente leitura (val) por padrão. Declare variáveis ​​mutáveis ​​(var) somente se necessário.

## Modelos de String

- Você pode usar expressões de modelo para acessar dados armazenados em variáveis ​​e outros objetos e convertê-los em strings.

```Kotlin
fun main() { 
    val customers = 10
    println("There are $customers customers")
    // There are 10 customers

    println("There are ${customers + 1} customers")
    // There are 11 customers
}
```

- Você notará que não há nenhum tipo declarado para variáveis. O Kotlin inferiu o tipo em si: Int.

## Tipos básicos

```Kotlin
fun main() {
    var customers = 10

    // Some customers leave the queue
    customers = 8

    customers = customers + 3 // Example of addition: 11
    customers += 7            // Example of addition: 18
    customers -= 3            // Example of subtraction: 15
    customers *= 2            // Example of multiplication: 30
    customers /= 3            // Example of division: 10

    println(customers) // 10
}
```

No total, Kotlin tem os seguintes tipos básicos:

 | Categoria                 | Tipos básicos                     | Código de exemplo                              |
|---------------------------|----------------------------------|-----------------------------------------------|
| **Inteiros**              | Byte, Short, Int, Long          | `val year: Int = 2020`                        |
| **Inteiros sem sinal**    | UByte, UShort, UInt, ULong      | `val score: UInt = 100u`                      |
| **Números de ponto flutuante** | Float, Double             | `val currentTemp: Float = 24.5f`, `val price: Double = 19.99` |
| **Booleanos**             | Boolean                         | `val isEnabled: Boolean = true`               |
| **Caracteres**           | Char                            | `val separator: Char = ','`                   |
| **Strings**              | String                          | `val message: String = "Hello, world!"`       |

Parar declarar uma variável sem inicializá-la, especifique seu tipo com ":", Por exemplo:

```Kotlin
fun main() {
    // Variable declared without initialization
    val d: Int
    // Variable initialized
    d = 3

    // Variable explicitly typed and initialized
    val e: String = "hello"

    // Variables can be read because they have been initialized
    println(d) // 3
    println(e) // hello
}
```
Se você não inicializar uma variável antes de lê-la, verá um erro:
```Kotlin
fun main() {
    // Variable declared without initialization
    val d: Int

    // Triggers an error
    println(d)
    // Variable 'd' must be initialized
}
```
## Coleções

Kotlin tem as seguintes coleções para agrupar itens:

| Tipo de Coleção | Descrição |
|----------------|-----------|
| **Listas**     | Coleções ordenadas de itens |
| **Conjuntos**  | Coleções únicas e não ordenadas de itens |
| **Mapas**      | Conjuntos de pares de chave-valor onde as chaves são únicas e mapeadas para apenas um valor |

Cada tipo de coleção pode ser mutável ou somente leitura.

**Lista**:
As listas armazenam itens na ordem em que são adicionados e permitem itens duplicados.

Para criar uma lista somente leitura, use a ``listOf()`` function.
Para criar uma lista mutável, use ``mutableListOf()`` function.

Ao criar listas, o Kotlin pode inferir o tipo de itens armazenados. Para declarar o tipo explicitamente, adicione o tipo entre colchetes angulares <> após a declaração da lista:

```Kotlin
fun main() { 
    // Read only list
    val readOnlyShapes = listOf("triangle", "square", "circle")
    println(readOnlyShapes)
    // [triangle, square, circle]

    // Mutable list with explicit type declaration
    val shapes: MutableList<String> = mutableListOf("triangle", "square", "circle")
    println(shapes)
    // [triangle, square, circle]
}
```

> 📖 Para evitar modificações indesejadas, você pode criar uma visualização somente leitura de uma lista mutável atribuindo-a a List:

```Kotlin
val shapes: MutableList<String> = mutableListOf("triangle", "square", "circle")
val shapesLocked: List<String> = shapes
```
> Isso também é chamado de **fundição**.

As listas são ordenadas, portanto, para acessar um item em uma lista, use o operador de acesso indexado []:

```Kotlin
fun main() { 
    val readOnlyShapes = listOf("triangle", "square", "circle")
    println("The first item in the list is: ${readOnlyShapes[0]}")
    // The first item in the list is: triangle
}
```
Para obter o primeiro ou o último item de uma lista, use as funções ``.first()`` e ``.last()`` respectivamente:

```Kotlin
fun main() { 
    val readOnlyShapes = listOf("triangle", "square", "circle")
    println("The first item in the list is: ${readOnlyShapes.first()}")
    // The first item in the list is: triangle
}
```

> ``.first()`` e ``.last()`` functions são exemplos de **funções de extensão**. Para chamar uma função de extensão em um objeto, escreva o nome da função após o objeto anexado a um ponto "."
> 

Para obter o número de itens em uma lista, use a ``.count()`` function:

```Kotlin
fun main() { 
    val readOnlyShapes = listOf("triangle", "square", "circle")
    println("This list has ${readOnlyShapes.count()} items")
    // This list has 3 items
}
```
Para verificar se um item está em uma lista, use o `in` operador:

```Kotlin
val readOnlyShapes = listOf("triangle", "square", "circle")
println("circle" in readOnlyShapes)
//true
```

Para adicionar ou remover itens de uma lista mutável, use as funções `.add()` e `.remove()` respectivamente:

```Kotlin
fun main() { 
    val shapes: MutableList<String> = mutableListOf("triangle", "square", "circle")
    // Add "pentagon" to the list
    shapes.add("pentagon") 
    println(shapes)  
    // [triangle, square, circle, pentagon]

    // Remove the first "pentagon" from the list
    shapes.remove("pentagon") 
    println(shapes)  
    // [triangle, square, circle]
}
```

## Set
Enquanto as listas são ordenados e permitem itens duplicados, os conjuntos **não são ordenados** e armazenam apenas itens **únicos**.

Para criar um conjunto somente leitura `(Set)` use a `setOf` function.
Para criar um conjunto mutável `MutableSet`, use a `mutableSetOf` function.

Ao criar conjuntos, o Kotlin pode inferir o tipo de itens armazenados. Para declrarar o tipo explicitamente, adicione o tipo entre colchetes angulares `<>` após a declaração do conjunto.

```Kotlin
fun main() {
    // Read-only set
    val readOnlyFruit = setOf("apple", "banana", "cherry", "cherry")
    // Mutable set with explicit type declaration
    val fruit: MutableSet<String> = mutableSetOf("apple", "banana", "cherry", "cherry")

    println(readOnlyFruit)
    // [apple, banana, cherry]
}
```
Você pode ver no exemplo anterior que, como os conjuntos contêm apenas elementos único, o "cherry" item duplicado é descartado.

> 📖 Para evitar modificações indesejadas, você pode criar uma visualização somente leitura de um conjunto mutável atribuindo-a a Set:

```Kotlin
val fruit: MutableSet<String> = mutableSetOf("apple", "banana", "cherry", "cherry")
val fruitLocked: Set<String> = fruit
```
>  💚 Como os conjuntos **não são ordenados**, você não pode acessar um item em um índice específico.

Para obter o número de itens em um conjunto, use a `.count()` function:
```Kotlin
fun main() { 
    val readOnlyFruit = setOf("apple", "banana", "cherry", "cherry")
    println("This set has ${readOnlyFruit.count()} items")
    // This set has 3 items
}
```
Para verificar se um item está em um conjunto, use o `in` operator:
```Kotlin
fun main() {
    val readOnlyFruit = setOf("apple", "banana", "cherry", "cherry")
    println("banana" in readOnlyFruit)
    // true
}
```

Para adicionar ou remover itens de um conjunto mutável, usa as funções `.add()` e `remove()` respectivamente:

```Kotlin
fun main() { 
    val fruit: MutableSet<String> = mutableSetOf("apple", "banana", "cherry", "cherry")
    fruit.add("dragonfruit")    // Add "dragonfruit" to the set
    println(fruit)              // [apple, banana, cherry, dragonfruit]

    fruit.remove("dragonfruit") // Remove "dragonfruit" from the set
    println(fruit)              // [apple, banana, cherry]
}
```

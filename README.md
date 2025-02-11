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




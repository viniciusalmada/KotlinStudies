# KotlinStudies
## Resumão Kotlin
### Try Kotlin
Try Kotlin é um site para rodar os códigos em Kotlin, pode ser acessado em <http://try.kotlinlang.org>. Basta digitar os códigos e rodar. Também é possível converter código Java para Kotlin.

### Funções `print` e `println`
Comandos usados para imprimir no console:
```kotlin
// Código
fun main(args: Array<String>){
    print("Hello World!")
    println("Hello, World!")
    println("Kotlin")
}

// Resultado
Hello, World!Hello World!
Kotlin
```
### String Templates
Para imprimir variáveis no console pode se usar a sintaxe `${variável}` ou `${objeto.propriedade}` dentro de strings.
```kotlin
fun main(args: Array<String>){
    var nome = "Ricardo"
    println("Olá $nome)
    println("$nome possui ${nome.lenght} caracteres")
    val msg = "Meu nome é $nome"
    println(msg)
}

// Resultado
Olá Ricardo
Ricardo possui 7 caracteres
Meu nome é Ricardo
```

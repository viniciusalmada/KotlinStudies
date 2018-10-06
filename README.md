# Estudos em Kotlin
## Tópicos importantes
### 1. Try Kotlin
Try Kotlin é um site para rodar os códigos em Kotlin, pode ser acessado em <http://try.kotlinlang.org>. Basta digitar os códigos e rodar. Também é possível converter código Java para Kotlin.

### 2. Funções `print` e `println`
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
### 3. String Templates
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
### 4. Variáveis com `var` e `val`
Variáveis são criadas usando a sintaxe:
```kotlin
var nome:String = "Ricardo"
```
O tipo da variável pode ser se o valor for atribuído.

```kotlin
var nome = "Ricardo"
```
A principal diferença entre o uso do `var` e `val` é a possibilidade de alterar o valor da variável. Variáveis criadas com `val` são similares a variáveis `final` do Java, não podem ter seu valor alterado; o uso do `var` tem o objetivo contrário.
### 5. Conversão de tipos: `as` e `is`
O modo de se fazer _cast_ em Kotlin faz uso da palavra-chave `as` 



# Estudos em Kotlin
## Tópicos importantes
### 1. Introdução
**Kotlin** é uma linguagem de programação criada pela _JetBrains_, lançada em 2011 para ser usada dentro da empresa em seus processos internos. 
No _Google I/O 2017_, a **Kotlin** foi oficialmente anunciada como linguagem de programação oficial para o desenvolvimento de aplicativos Android.
Tem uma sintaxe muito simples e agradável, que é compilada para ser executada na _JVM (Java Virtual Machine)_ e por isso possui 100% de interoperabilidade com a linguagem Java, mas com a vantagem de usar muito menos código.
```Java
View btAgenda = findViewById(R.id.btAgenda);
btAgenda.setOnClickListener(new View.OnClickListener() {
	@Override
	public void onClick(View v){
		agendar();
	}
} 
```
O código acima, em Java, faz o tratamento do evento de clique a um botão. Veja abaixo o mesmo código em Kotlin:
```Kotlin
findViewById<Button>(R.id.btAgendar).setOnClickListener{agendar()}
```
### 2. Try Kotlin
Try Kotlin é um site para rodar os códigos em Kotlin, pode ser acessado em <http://try.kotlinlang.org>. Basta digitar os códigos e rodar. Também é possível converter código Java para Kotlin.

### 3. Funções `print` e `println`
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
### 4. String Templates
Para imprimir variáveis no console pode se usar a sintaxe `${variável}` ou `${objeto.propriedade}` dentro de strings.
```kotlin
fun main(args: Array<String>){
    var nome = "Ricardo"
    println("Olá $nome")
    println("$nome possui ${nome.lenght} caracteres")
    val msg = "Meu nome é $nome"
    println(msg)
}

// Resultado
Olá Ricardo
Ricardo possui 7 caracteres
Meu nome é Ricardo
```
### 5. Variáveis com `var` e `val`
Variáveis são criadas usando a sintaxe:
```kotlin
var nome:String = "Ricardo"
```
O tipo da variável pode ser se o valor for atribuído.

```kotlin
var nome = "Ricardo"
```
A principal diferença entre o uso do `var` e `val` é a possibilidade de alterar o valor da variável. Variáveis criadas com `val` são similares a variáveis `final` do Java, não podem ter seu valor alterado; o uso do `var` tem o objetivo contrário.
### 6. Conversão de tipos: `as` e `is`
O modo de se fazer _cast_ em Kotlin faz uso da palavra-chave `as`. Caso a conversão não seja possível, será lançada uma _Exception_, para evitar isso, pode-se usar um _safe cast_ com `as?` que retorna `null` caso não aconteça a conversão.
Para se fazer uma verificação do tipo de uma variável é utilizada o `is` como um operador booleano, é semelhante ao `instanceOf` do Java.
```kotlin
// Código
fun main(args: Array<String>) {
    val s:Any = "Ricardo"
    println(s as String)
    println(s as? Int)
    if (s is String){
        println("$s é uma Strong") // smart cast
    }
}

// Resultado
Ricardo
null
Ricardo é uma String
```
### 7. Objetos nulos (_Null Safety_)
Kotlin não permite valores nulos para variáveis, a não ser que isso seja explicitamente indicado.
```kotlin
// Código
fun main(args: Array<String>) {
   var nome = "Ricardo"
   nome = null // Error
}
```
O código acima lança uma _Exception_ em tempo de compilação, pois a variável `nome` não pode receber um valor nulo. Para que esse código seja válido, a variável precisa indicar que pode receber valor nulo com o operador `?`:
```kotlin
// Código
fun main(args: Array<String>) {
   var nome:String? = "Ricardo"
   println("Olá $nome")
   nome = null // Ok
   println("Olá $nome")
}

// Resultado
Olá Ricardo
Olá null
```
Quando se indica uma variável como nula, na compilação, essa "nulidade" precisa ser tratada, ou um erro será lançado. Por exemplo:
```kotlin
// Código
fun main(args: Array<String>) {
   var nome:String? = "Ricardo"
   println("Olá $nome")
   nome = null // Ok
   println("Olá $nome")
   println("$nome possui ${nome.lenght} caracteres") // Error
}
```
O compilador lança um erro pois a variável `nome` pode ser nula e isso pode dar problema, por isso é necessário uma verificação para a correta execução, dessa forma:
```kotlin
// Código
fun main(args: Array<String>) {
   var nome:String? = "Ricardo"
   println("Olá $nome")
   nome = null // Ok
   println("Olá $nome")
   if (nome != null){
	   println("$nome possui ${nome.lenght} caracteres")
   }
}

// Resultado

```

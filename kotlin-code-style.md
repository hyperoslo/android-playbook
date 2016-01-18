#Kotlin play book

The general coding conventions : https://kotlinlang.org/docs/reference/coding-conventions.html

#Classes and Inheritance

##Constructors

As often as possible we should specify if the constructor properties are mutable
(var) or read-only (val) :

```
class Person(val firstName: String, val lastName: String, var age: Int) {
    // ...
}
```
## Companion object

It should be place at the beginning of its parent class :

```
class Person(val firstName: String, val lastName: String, var age: Int) {

    companion object {

        val A_CONSTANT = "constant"

    }

    private val anAttribute = 0

    public fun aMethod () {
        //...
    }

}
```

#Extensions

I suggest we create one extension file for each Type we need :

```
- StringExtension.kt
- BitmapExtension.kt
- ContextExtension.kt
...
```

#Object Expressions and Declarations

##Object expressions

To avoid too long method, we should externalize object expressions as properties
:

```
class Person(val firstName: String, val lastName: String, var age: Int) {

    private val anAttribute = object : MyJavaInterface() {
        //...
    }

    public fun aMethod () {
        button.setOnSomeClick( anAttribute )
    }

}
```

#Delegated Properties

##Standard Delegates

We should use the standard delegates `lazy`as often as possible in order to have
lazy loading properties :

```
val myValue : String by lazy {
    someInit() //executed only at the first access
    callToAFunctionReturningAStringValue()
}
```
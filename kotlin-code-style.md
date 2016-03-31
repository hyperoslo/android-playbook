# Kotlin play book

Our conventions for writing Kotlin code is based on the coding conventions from
the [Kotlin documentation].

[kotlin documentation]: https://kotlinlang.org/docs/reference/coding-conventions.html

# Classes and Inheritance

## Constructors

As often as possible we should specify if the constructor properties are mutable
(`var`) or read-only (`val`):

```kotlin
class Person(val firstName: String, val lastName: String, var age: Int) {
    // ...
}
```

## Companion object

It should be placed at the beginning of its wrapper class:

```kotlin
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

# Extensions

When adding extensions to external classes, make separate files for each type
and name them _<Type>Extensions.kt_:

```
- StringExtensions.kt
- BitmapExtensions.kt
- ContextExtensions.kt
- ...
```

# Object Expressions and Declarations

## Object expressions

To avoid writing methods that are too long, externalize object expressions as
properties:

```kotlin
class Person {

    private val anAttribute = object : MyJavaInterface() {
        // ...
    }

    fun aMethod() {
        button.setOnSomeClick(anAttribute)
    }

}
```

# Delegated Properties

## Standard Delegates

We should use the standard delegates `lazy` as often as possible in order to
have lazy loading properties:

```kotlin
val myValue : String by lazy {
    someInit()
    functionReturningAStringValue()
}
```

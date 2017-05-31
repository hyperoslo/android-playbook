# Kotlin play book

Our conventions for writing Kotlin code is based on the coding conventions from
the [Kotlin documentation].

[kotlin documentation]: https://kotlinlang.org/docs/reference/coding-conventions.html

# Classes and Inheritance

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

## Constructors

As often as possible we should specify if the constructor properties are mutable
(`var`) or read-only (`val`):

```kotlin
class Person(val firstName: String, val lastName: String, var age: Int) {
    // ...
}
```

## Methods

If your method has an empty body, use the `Unit` type instead of empty bracket body : 

```kotlin
fun anEmptyFunction() = Unit
```

if you are implementing an interface, and only one method is relevant for you, place all the empty one first :
```kotlin
object : someInterface {
  fun methodOne() = Unit
  fun methodThree() = Unit
  fun methodTwo() {
    //your code here
  }
}
```

# Extensions

When adding extensions to external classes, create a extension package and make separate files for each type:

```
- extensions
  - StringExtensions.kt
  - BitmapExtensions.kt
  - ...
```

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

Initialize class properties as primary constructor parameters instead of in an `init` block.

**DO:**

```kotlin
class Person(val firstName: String, val lastName: String, var age: Int) {
    // ...
}
```

**DON'T:**

```kotlin
class Person(firstName: String, lastName: String, age: Int) {
  val firstName: String
  val lastName: String
  var age: Int

  init {
    this.firstName = firstName
    this.lastName = lastName
    this.age = age
  }

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

# Data classes

Primary constructors in data classes should be written with a single property on each line, and not begin on the line of the class definition:

**DO:**

```kotlin
data class Person(
    val firstName: String,
    val lastName: String,
    var age: Int
)
```

**DON'T:**

```kotlin
data class Person(val firstName: String,
                  val lastName: String,
                  var age: Int)
```

# Extensions

When adding extensions to external classes, create a extension package and make separate files for each type:

```
- extensions
  - StringExtensions.kt
  - BitmapExtensions.kt
  - ...
```

# Code style

In order for code to look familiar to all developers and consistent across code
bases, it is important to have certain rules and conventions for how the code
should be styled. Examples of this is rules for indentation, rules for spacing
between methods, variables and statements, grouping of import statements and
more.

## Indentation

Having a single set of rules when it comes to indentation makes the code base
feel a lot more consistent when multiple developers are working on it. Following
the official Android style guides for indentation, we use spaces – not tabs – to
indent our Java code. We also make sure to use four spaces for regular
indentation, like in the example below:

```java
class MainActivity {

    @Override
    public onCreate(Bundle savedInstanceState) {
        // Make all kinds of things. All kinds...
    }

}
```

Also, notice by the example above, that we keep annotations on the same level of
indentation as the element it is connected to. The exception to this rule, is if
the annotation is written on the same line. For example, with the exquisite
ButterKnife library:

```java
class LoginActivity {

    @Bind(R.id.username_text_view) TextView loginTextView;
    @Bind(R.id.password_text_view) TextView passwordTextView;

}
```

When breaking a statement into multiple lines, it is also a good idea this with
indentation. Again, following the official guidelines, we use eight spaces for
this kind of indentation, to separate it from regular indentation. An example:

```java
chat.sendMessage("Duke Nukem", "Bubble Gum",
        "I'm here to kick ass and chew bubble gum. And I'm all outta gum!");
```

# Brackets

If you decide to use if statement, while loop etc in one line we recommend not to use brackets in this case at all. An example:

```java
if (isRefreshed) invalidate();
```

For any other case we recommend to use brackets. Examples:

```java
if (isNew) {
    d// ...
} else {
    // ...
}

if (isNew) {
    // ...
} else if(isOld) {
    // ...
}

while (true) {
    // ...
}

```

or


```java
try {
    // ...
} catch {
    // ...
} finally {
    // ...
}

```

Please notice that we recommend to continue writing next block of the statement on the same line as closing bracket of previous block. An Example:

```java
if (isNew) {
    // ...
} else {
    // ...
}
```

not

```java
if (isNew) {
    // ...
} 
else {
    // ...
}

if (isNew) {
    // ...
} 
else 
{
    // ...
}
```




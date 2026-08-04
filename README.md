# JavaNotes
## Java Syntax

- Every line of Java code must be inside a **class**.
- The **class name** should start with an uppercase letter (by convention), e.g., `MyClass`.
- The **Java file name** and the **public class name** must be the same.
  - Example: If the class is `MyClass`, the file must be named **`MyClass.java`**.
- Java is **case-sensitive**.
  - `MyClass`, `myClass`, and `myclass` are all considered different names.

## Example

```java
public class MyClass {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

**File name:** `MyClass.java` ✅

> **Note:** If you save this code as `myclass.java` or `Hello.java`, it will cause a compilation error because the **public class name** and the **file name** do not match.
## The `main()` Method

The `main()` method is the entry point of every Java program. It is where the program starts executing.

```java
public static void main(String[] args)
```
## `System.out.println()`

`System.out.println()` is used to **print text or values to the screen**.

#### Example

```java
public static void main(String[] args) {
    System.out.println("Hello World");
}
```

**Output:**
```text
Hello World
```

#### Simple Breakdown

- `System` → Built-in Java class.
- `out` → Represents output.
- `println()` → Prints the content and moves to a **new line**.
- `{ }` → Marks the beginning and end of a block of code.
- `;` → Every Java statement must end with a **semicolon**.

> **Simple meaning:** `System.out.println()` = **"Print this on the screen and move to the next line."**

Any code placed inside the `main()` method will be executed.


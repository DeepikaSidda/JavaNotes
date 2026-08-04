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

---

## The `main()` Method

The `main()` method is the **entry point** of every Java program. It is where the program starts executing.

```java
public static void main(String[] args)
```

Any code placed inside the `main()` method will be executed.

---

## `System.out.println()`

`System.out.println()` is used to **print text or values to the screen**.

### Example

```java
public static void main(String[] args) {
    System.out.println("Hello World");
}
```

**Output:**

```text
Hello World
```

### Simple Breakdown

- `System` → Built-in Java class.
- `out` → Represents output.
- `println()` → Prints the content and moves to a **new line**.
- `{ }` → Marks the beginning and end of a block of code.
- `;` → Every Java statement must end with a **semicolon**.

> **Simple meaning:** `System.out.println()` = **"Print this on the screen and move to the next line."**

---

## Statements

In Java, **most lines of code that end with a semicolon (`;`) are statements**. Each statement tells the computer to perform one task.

### Example 1

```java
System.out.println("Hello");
```

This is a statement because:
- It ends with a semicolon (`;`).
- It tells the computer to print **"Hello"** on the screen.

### Example 2

```java
int age = 20;
```

This is also a statement because it tells the computer to create a variable named `age` and store the value `20`.

> Java executes statements **one by one, from top to bottom**, in the order they are written.

**Simple Definition:**  
A **statement** is an instruction in Java that tells the computer to do something. Most statements end with a semicolon (`;`).

---

## Difference Between `print()` and `println()`

The only difference is:

- `println()` **prints the output and moves the cursor to the next line**.
- `print()` **prints the output but stays on the same line**.

> **Note:** Each call to `System.out.print()` accepts only **one argument**. To print multiple values, combine them using the `+` operator or call `print()` multiple times.

### Example

```java
System.out.print("Hello ");
System.out.print("World");
```

**Output:**

```text
Hello World
```

---

## Java Comments

Comments are used to **explain the code** and make it easier to understand. They are **ignored by the Java compiler**, so they are **not executed**.

### Types of Comments

- `//` → **Single-line comment** (used for a comment on one line).
- `/* ... */` → **Multi-line comment** (used for comments that span multiple lines).
---
### Adding Spaces and Commas

`System.out.print()` does **not** automatically add spaces or commas between values. If you want spaces (`" "`) or commas (`", "`), you must include them yourself in the string.

#### Example

```java
System.out.print("Apple, " + "Banana, " + "Orange");
```

**Output:**

```text
Apple, Banana, Orange
```

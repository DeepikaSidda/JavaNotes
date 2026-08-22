
# Java Classes and Objects 

## 1. First understand the big picture

In Java:

```
Class
  ↓  Blueprint / design
Object
  ↓  Actual thing created from that blueprint
```

For example:

```
Class  → Car
Objects → car1, car2, car3
```

You can create many cars from one `Car` class.

## 2. What exactly is a Class?

A class is a definition of what an object should contain and what it should be able to do.

```java
class Car {
    String brand;
    String color;

    void start() {
        System.out.println("Car Started");
    }
}
```

This class describes a car. It says every `Car` object can have:

- `brand`
- `color`

and can perform:

- `start()`

But this class itself is **not** a particular car. It is just the design.

## 3. What are `brand` and `color`?

These are called **fields** or **instance variables**.

```java
class Car {
    String brand;
    String color;
}
```

Think of them as the data/properties of a car.

```
Car
 ├── brand
 └── color
```

Different objects can have different values.

## 4. What is `start()`?

This is a **method**.

```java
void start() {
    System.out.println("Car Started");
}
```

A method represents behavior/action.

- **Fields**  → What the object *has*
- **Methods** → What the object *can do*

For a car:

- Properties: `brand`, `color`
- Behavior: `start()`

## 5. Does the class create an object?

**No.** This is very important.

When you write:

```java
class Car {
    String brand;
    String color;
}
```

you have only defined the *structure*. You haven't created a particular car yet. You need to create an object using `new`.

## 6. Creating an Object

```java
Car car1 = new Car();
```

This line has three important parts:

```
Car        car1        new Car()
 ↑          ↑             ↑
class
/type     reference      creates
         variable       object
```

## 7. `Car` on the left

```java
Car car1
```

The first `Car` tells Java that `car1` can refer to a `Car` object. It's the reference variable's type.

## 8. `car1`

`car1` is a **reference variable** that refers to a `Car` object.

Beginners often say "car1 is the object." Technically, that's not quite correct.

## 9. `new Car()`

This is where the actual object is created. `new Car()` means: create a new `Car` object. Java allocates memory for it.

```
Heap
┌─────────────────────┐
│      Car object     │
│ brand = null        │
│ color = null        │
└─────────────────────┘
```

And `car1` refers to that object:

```
car1
  │
  ↓
┌─────────────────────┐
│      Car object     │
│ brand = null        │
│ color = null        │
└─────────────────────┘
```

## 10. Why are `brand` and `color` initially `null`?

Because they are instance variables of type `String`. When an object is created, Java gives default values:

```
String  → null
int     → 0
double  → 0.0
boolean → false
```

So initially `brand = null` and `color = null`.

## 11. Assigning values

```java
car1.brand = "Toyota";
car1.color = "White";
```

This means: go to the object referred to by `car1` and set its `brand` and `color`.

```
car1
  ↓
┌─────────────────────┐
│ brand = "Toyota"    │
│ color = "White"     │
└─────────────────────┘
```

## 12. Why do we use `car1.brand`?

Because `brand` belongs to the `Car` object. The dot `car1.brand` means: access the `brand` field of the object referred to by `car1`. Similarly for `car1.color`.

## 13. Calling the method

```java
car1.start();
```

The dot means: access the `start()` method of the object referred to by `car1`.

Output:

```
Car Started
```

## 14. Complete execution

```java
class Car {
    String brand;
    String color;

    void start() {
        System.out.println("Car Started");
    }
}

public class Main {
    public static void main(String[] args) {
        Car car1 = new Car();
        car1.brand = "Toyota";
        car1.color = "White";
        System.out.println(car1.brand); // Toyota
        System.out.println(car1.color); // White
        car1.start();                    // Car Started
    }
}
```

Step by step:

```
Car car1 = new Car();      car1 → { brand = null,   color = null  }
car1.brand = "Toyota";     car1 → { brand = Toyota, color = null  }
car1.color = "White";      car1 → { brand = Toyota, color = White }
```

Output:

```
Toyota
White
Car Started
```

## 15. Why can we create multiple objects?

Define the class once, then create many objects:

```java
Car car1 = new Car();
Car car2 = new Car();
Car car3 = new Car();
```

```
car1 ──→ Car object 1   brand = Toyota  color = White
car2 ──→ Car object 2   brand = Honda   color = Black
car3 ──→ Car object 3   brand = BMW     color = Blue
```

They all follow the same class structure, but their data can differ.

## 16. This is the key difference

The class says every `Car` *has* `brand`, `color` and *can* `start()`. But each object has its own values.

```
car1                    car2
  ↓                       ↓
┌──────────────┐       ┌──────────────┐
│ Toyota       │       │ BMW          │
│ White        │       │ Black        │
└──────────────┘       └──────────────┘
```

Same class (`Car`), different objects (`car1`, `car2`), different data.

## 17. Very Important: Objects are independent

```java
car1.color = "White";
car2.color = "Black";
car1.color = "Red";
```

Now `car1 → Red`, `car2 → Black`. Changing one does not change the other — they are two different objects.

## 18. One Class → Many Objects

```
              Car class
             /    |    \
          car1  car2  car3
            ↓     ↓     ↓
         Object Object Object
```

The class is the common structure; the objects are the individual instances.

## 19. What does "Instance" mean?

When we say "car1 is an instance of Car," it means `car1` refers to an object created from the `Car` class.

```
Car        → class
car1       → reference variable
new Car()  → creates an instance/object
```

Object and instance are often used interchangeably.

## 20. Class vs Object vs Reference Variable

For `Car car1 = new Car();`

- `Car` → the class/type
- `new Car()` → creates the object
- `car1` → reference variable

Don't think `car1 = object`. A better model:

```
car1 = reference
          ↓
       object
```

## 21. What happens if we create two objects?

```java
Car car1 = new Car();
Car car2 = new Car();
```

```
car1 ──→ Object 1
car2 ──→ Object 2
```

They are separate objects.

## 22. What happens if we do this?

```java
Car car1 = new Car();
Car car2 = car1;
```

We did **not** create another object. There is still only one:

```
car1 ─────┐
          ↓
       Car object
          ↑
car2 ─────┘
```

So:

```java
car1.color = "Red";
System.out.println(car2.color); // Red
```

Both references point to the same object.

## 23. Class contains both Data and Behavior

```java
class Student {
    String name;   // data
    int age;       // data

    void study() {                       // behavior
        System.out.println("Student is studying");
    }

    void introduce() {                   // behavior
        System.out.println("My name is " + name);
    }
}
```

An object contains **State + Behavior**.

## 24. What is State?

The current values of an object's fields.

```java
Student s1 = new Student();
s1.name = "Deepika";
s1.age = 21;
```

State of `s1`: `name = Deepika`, `age = 21`. Another object with `name = Rahul`, `age = 22` has a different state.

## 25. What is Behavior?

Methods represent what the object can do.

```java
void study() {
    System.out.println("Studying...");
}
```

```
State    → name, age
Behavior → study()
```

## 26. Real-Life Example: Student

```java
class Student {
    String name;
    int age;

    void study() {
        System.out.println(name + " is studying");
    }
}

Student s1 = new Student();
Student s2 = new Student();

s1.name = "Deepika"; s1.age = 21;
s2.name = "Rahul";   s2.age = 22;
```

```
s1                       s2
 ↓                        ↓
┌─────────────────┐      ┌─────────────────┐
│ name = Deepika  │      │ name = Rahul    │
│ age = 21        │      │ age = 22        │
└─────────────────┘      └─────────────────┘
```

The same method operates on the particular object that called it.

## 27. Why do we need Objects?

A class defines *what a student should have*, but an app must represent individual entities: Deepika, Rahul, Priya, Kiran.

```
Class   → defines the structure
Objects → represent individual entities
```

## 28. Class vs Object — table

| Class | Object |
|-------|--------|
| Blueprint / design | Actual instance created from the class |
| Defines what data exists | Contains actual data |
| Defines methods / behavior | Can use those methods |
| One class can be defined | Many objects can be created |
| Example: `Car` | Example: `car1`, `car2` |
| Doesn't represent one particular car | Represents a particular car |

Technical point: `car1` itself is a reference variable, while the object is created by `new Car()`.

## 29. The Most Important Line

```java
Car car1 = new Car();
```

Read it as: *"Create a new Car object and store a reference to that object in car1."*

```
Car       car1       =       new Car();
 ↑         ↑                     ↑
type    reference             creates
        variable              object
```

## ⭐ Final Mental Model

```
CLASS                       CLASS
┌─────────────┐               Car
│ House       │                ↓
│ rooms       │        ┌───────┼────────┐
│ color       │        ↓       ↓        ↓
│ doors       │       car1    car2     car3
└─────────────┘        ↓       ↓        ↓
      ↓              Toyota    BMW     Honda
 House1 House2       White    Black     Red
```

Remember these 5 things:

1. **Class** → blueprint / template
2. **Object** → actual instance created from the class
3. **new** → creates the object
4. **Reference variable** → holds a reference to the object
5. One class can create many independent objects

The most important line:

```java
Car car1 = new Car();
// Car = type/class → car1 = reference → new Car() = creates the object
```

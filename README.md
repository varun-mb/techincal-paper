# <p align="center">Object Oriented Programming (OOPs)</p>

## Introduction to Object Oriented Programming (OOPs)

OOPs is a programming paradigm based on the concept of "classes" and "objects". A class is a blueprint for creating objects. An object is an instance of a class, i.e., it's an identifiable entity with some characteristics (attributes) and behavior (functions). The diagram below shows the relation between class, objects, functions and attributes using the example of a human being:-

<img src=https://i.pinimg.com/564x/ca/cb/2a/cacb2a4f75eb17c96fa83669fc62af1e.jpg height=400px width=420px></img>

In the above example, humans can be considered a class (a blueprint) and every distinct individual is an object (an instance) of the "human" class. An individual can possess attributes like height, weight and hobbies, which are unique for every individual. Also, humans can exhibit certain behaviors (functions) like running, kicking and jumping.<br>
The main aim of object-oriented programming is to implement real-world entities into code. Some popular programming languages which support OOPs are -  Java, C++, JavaScript, Python, R, etc.

## Object Oriented Programming Concepts

\[Note: Code snippets are written in Java language]

### Classes and Objects

A class categorises a real world entity and provides a blueprint for an object. Objects are an instance of a class. Below is a code snippet which demonstrates the implementation of class and objects.

```java
public class Car{
  String name;
  int speed;
  
  public Car() {
    String name= "";
    int speed=0;
  }
  
  void startEngine(){
    System.out.println("Engine started");
  }
  
  public static void main(String[] args){
    Car c1=new Car();
    Car c2=new Car();
    c1.name="Hyundai"; c1.speed=100;
    c2.name="Maruti";  c2.speed=90;
    }
}
```

As per the above code snippet, `Car` is a class that provides a blueprint for objects `c1` and `c2` (attributes - `name` and `speed`; and function - `startEngine()`). The attributes - `name` and `speed`, are the characteristics of the objects. The function - `startEngine()` depicts the behavior of the objects.

### The 4 Pillars of Object Oriented Programming

1. **Abstraction:** <br>
Data Abstraction may also be defined as the process of identifying only the required characteristics of an object ignoring the irrelevant details. The properties and behaviours of an object differentiate it from other objects of similar type and also help in classifying/grouping the objects. One way to achieve abstraction in JAVA is to use abstract class and functions via the `abstract` keyword:

    ```java
    abstract class Bike{  
      abstract void run();  
    }  
    class Honda4 extends Bike{  
      void run(){
        System.out.println("running safely");
        }  
      public static void main(String args[]){  
        Bike obj = new Honda4();  
        obj.run();  
      }  
    } 
    ```

    In the above code snippet, the abstract class `Bike` only shows the function `run()` of the bike but not it's internal working. Hence, data abstraction is achieved.

2. **Inheritance:** <br>
Inheritance in Java is a mechanism in which one object acquires all the properties and behaviors of a parent object. It is the process by which one class is allowed to inherit the properties of another class. Inheritance enables us to achieve code reusability. A sub-class can inherit the properties of a parent class via the `extends` keyword. Below code snippet demonstrates Inheritance in JAVA:

    ```java
    class Employee{  
    float salary;
    float bonus;
    }  
    class Programmer extends Employee{    
    public static void main(String args[]){  
      Programmer p1=new Programmer();
      p1.salary=100000;
      p1.bonus=p1.salary/15;
      System.out.println("Programmer salary is:"+p1.salary);  
      System.out.println("Bonus of Programmer is:"+p1.bonus);  
      }  
    }  
    ```

    In the above code snippet, the parent class Employee has the attributes - `salary` and `bonus`. A subclass `Programmer` inherits the properties of the parent class `Employee` via `extends` keyword. It allows us to skip re-writing the attributes for the `Programmer` class and enables code reusability.
    JAVA supports 3 types of inheritance - single (Class A <- Class B), multilevel (Class A <- Class B <- Class C) and heirarchical (Class A <- Class B, Class A <- Class C).

3. **Encapsulation:** <br> Encapsulation in Java is a process of wrapping code and data together into a single unit. A fully encapsulated class in JAVA hides it's data from other classes using the data hiding concept which can be achieved by setting all data members of a class `private`. Setter and Getter methods can allow us to enter and receive the data respectively.

    ```java
    public class Student{  
      private String name;  //private variable
      public String getName(){  //getter method for name
        return name;  
      }    
      public void setName(String name){  //setter method for name
        this.name=name  
      }  
    }
    ```
    
    As per above code snippet, the setter and getter methods, `getName()` and `setName()` allow us to enter data into, as well as receive it from, a private variable `name`.

4. **Polymorphism:** <br> In OOPs, Polymorphism is the concept that refers to the ability of a variable, function or object to take on multiple forms. To better understand polymorphism, we can take the real world example of a man who can be a husband, a father, a brother or an employee, and exhibits different behavior while serving different roles. Similarily, in OOPs, polymorphism allows us to define a single interface and have multiple implementations of the same. In JAVA, polymorphism is divided into 2 types:

    * **Compile-Time Polymorphism:**
    It is also known as static polymorphism. This type of polymorphism is achieved by function overloading or operator overloading. 

      ```java
      class Helper {
        static int Multiply(int a, int b){
          return a * b;
        }
        static int Multiply(int a, int b, int c){
          return a*b*c;
        }
      }
      class GFG {
        public static void main(String[] args){
          System.out.println(Helper.Multiply(2, 4));
          System.out.println(Helper.Multiply(2, 4, 6));
        }
      }
      ```

      As per the above code snippet, the function `Multiply()` serves 2 different functions of either multiplying 2 variables or 3 variables via function overloading. Hence, polymorphism is achieved.

    * **Runtime Polymorphism:**
    It is also known as Dynamic Method Dispatch. It is a process in which a function call to the overridden method is resolved at Runtime. This type of polymorphism is achieved by Method Overriding. Method overriding, on the other hand, occurs when a derived class has a definition for one of the member functions of the base class. That base function is said to be overridden.

      ```java
      class Parent {
        void Print(){
          System.out.println("parent class");
        }
      }
      class subClass extends Parent{
        void Print(){ 
          System.out.println("subclass1"); 
        }
      }
      class GFG {
        public static void main(String[] args)
        {
          Parent a;
          a = new subClass();
          a.Print();
        }
      }
      ```
      
      In the above code snippet, the `Print()` function of the parent class is overriden by the same function defined in the child class during runtime, since the object of child class - `subClass` is used to call the function. Hence, polymorphism is achieved.

## Advantages of Object Oriented Programming

### 1. Modularity

OOPs enables us to write modular codes which can help us with troubleshooting as we can figue out the exact module which throws an error and we don’t have to go line-by-line through all the code. Objects are self-contained, and each bit of functionality does its own thing while leaving the other bits alone.

### 2. Reuse of code through inheritance

Suppose that in addition to a Car object, a RaceCar and a Limousine objects are also needed. We see that there are certain commonalties between the objects. The RaceCar and Limousine objects share the traits of Car object with some extra addtional traits unique to each. This is where the inheritance technique saves out time. We can create a generic class `Car`, and then define the subclasses `RaceCar` and `Limousine` that are to inherit the generic class’s traits.

### 3. Flexibility through Polymorphism

As per the above example, say we need functions, like `driveCar()`, `driveRaceCar()` and `DriveLimousine()`. RaceCarDrivers share some traits with LimousineDrivers, but other things, like RaceHelmets and BeverageSponsorships, are unique. <br>
This is where object-oriented programming’s polymorphism comes into play. Because a single function can shape-shift to adapt to whichever class it’s in, we can create one function in the parent Car class called `drive()`, and save time by not creating separate functions for each car type. This function would work with the RaceCarDriver, LimousineDriver and so on.

### 4. Effective Problem Solving

Object-oriented programming enables us to take a huge problem and break it down to smaller problems. For each smaller problem, we can write a separate class which provides the required functionality. Also, the classes can be re-used, which makes it quicker to solve related problems.

## Resources

- [BuggyProgrammer - OOPs](https://buggyprogrammer.com/what-is-the-object-oriented-programming-2021/) <br>
- [Wikipedia - OOPs](https://en.wikipedia.org/wiki/Object-oriented_programming) <br>
- [JavaTPoint - Java OOPs Concepts](https://www.javatpoint.com/java-oops-concepts) <br>
- [GeeksForGeeks - Polymorphism in Java](https://www.geeksforgeeks.org/polymorphism-in-java/)<br>
- [W3Schools - Java OOPs](https://www.w3schools.com/java/java_oop.asp)<br>

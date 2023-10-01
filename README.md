# GoF_Csharp-Singleton_pattern

https://refactoring.guru/design-patterns/singleton

https://www.dotnettricks.com/learn/designpatterns/singleton-design-pattern-dotnet

The Gang of Four (GoF) design patterns are a collection of 23 design patterns that were introduced by Erich Gamma, Richard Helm, Ralph Johnson, and John Vlissides in their book "Design Patterns: Elements of Reusable Object-Oriented Software," published in 1994. These patterns provide solutions to common software design problems and help in creating flexible, maintainable, and scalable software systems. The patterns are categorized into three groups: Creational, Structural, and Behavioral patterns. Here's a brief overview of each pattern:

## Singleton pattern (Creational Patterns):
Ensures that "A CLASS HAS ONLY ONE INSTANCE" and provides a global point of access to that instance. This is useful when you want to control the number of instances of a class and ensure that all parts of the application access the same instance.

![image](https://github.com/luiscoco/GoF_Csharp-1.Singleton_pattern/assets/32194879/3726875a-cda9-4706-81da-f435a3ca7cfa)


##  Pattern - UML Diagram & Implementation
The UML class diagram for the implementation of the Singleton design pattern is given below:

![image](https://github.com/luiscoco/GoF_Csharp-1.Singleton_pattern/assets/32194879/d899fc9f-a15f-4f9d-ad28-f7ad918e56b0)

This is a class that is responsible for creating and maintaining its own unique instance.

## Singleton Pattern - Example

![image](https://github.com/luiscoco/GoF_Csharp-1.Singleton_pattern/assets/32194879/6058c16d-2e94-4479-8f39-4ba3130f5ee0)

## C# - First Sample Code

```csharp
/// <summary>
/// The 'Singleton' class
/// </summary>
public class Singleton
{
 // .NET guarantees thread safety for static initialization
 private static Singleton instance = null;
 private string Name{get;set;}
 private string IP{get;set;}
 private Singleton()
 {
 //To DO: Remove below line
 Console.WriteLine("Singleton Intance");

 Name = "Server1";
 IP = "192.168.1.23";
 }
 // Lock synchronization object
 private static object syncLock = new object();

 public static Singleton Instance
 {
 get
 {
 // Support multithreaded applications through
 // 'Double checked locking' pattern which (once
 // the instance exists) avoids locking each
 // time the method is invoked
 lock (syncLock)
 {
 if (Singleton.instance == null)
 Singleton.instance = new Singleton();

 return Singleton.instance;
 }
 }
 }

 public void Show()
 {
 Console.WriteLine("Server Information is : Name={0} & IP={1}", IP, Name);
 }

}

/// <summary>
/// Singleton Pattern Demo
/// </summary>
/// 
class Program
{
 static void Main(string[] args)
 {
 Singleton.Instance.Show();
 Singleton.Instance.Show();

 Console.ReadKey();
 }
}
```

## C# - Second Sample Code

```csharp
﻿using System;

class Program
{
    static void Main()
    {
        Singleton singleton = Singleton.GetInstance();
        Console.WriteLine(singleton.Function());
    }
}

public class Singleton
{
    private static Singleton instance;

    // Private constructor to prevent external instantiation
    private Singleton() { }

    public static Singleton GetInstance()
    {
        if (instance == null)
        {
            instance = new Singleton();
        }
        return instance;
    }

    public string Function() // Renamed the method to start with a capital letter
    {
        return "Hola";
    }

    // Add other methods and properties here
}
```

## How to setup Github actions

![Csharp Github actions](https://github.com/luiscoco/GoF_Csharp-1.Singleton_pattern/assets/32194879/8e86c080-bdd5-4a39-97ef-b877647a3217)


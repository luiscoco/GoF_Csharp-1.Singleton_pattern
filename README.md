# GoF_Csharp-Singleton_pattern

The Gang of Four (GoF) design patterns are a collection of 23 design patterns that were introduced by Erich Gamma, Richard Helm, Ralph Johnson, and John Vlissides in their book "Design Patterns: Elements of Reusable Object-Oriented Software," published in 1994. These patterns provide solutions to common software design problems and help in creating flexible, maintainable, and scalable software systems. The patterns are categorized into three groups: Creational, Structural, and Behavioral patterns. Here's a brief overview of each pattern:

## Singleton pattern (Creational Patterns):
Ensures that "A CLASS HAS ONLY ONE INSTANCE" and provides a global point of access to that instance. This is useful when you want to control the number of instances of a class and ensure that all parts of the application access the same instance.

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

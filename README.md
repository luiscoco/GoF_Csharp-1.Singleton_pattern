# GoF_Csharp-Singleton_pattern

The Singleton pattern ensures that "A CLASS HAS ONLY ONE INSTANCE" and provides a global point of access to that instance. This is useful when you want to control the number of instances of a class and ensure that all parts of the application access the same instance.

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

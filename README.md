# GoF_Csharp-Singleton_pattern

```csharp
﻿using System;

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

class Program
{
    static void Main()
    {
        Singleton singleton = Singleton.GetInstance();
        Console.WriteLine(singleton.Function());
    }
}
```

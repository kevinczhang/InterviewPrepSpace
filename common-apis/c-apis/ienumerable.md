---
description: >-
  Exposes an enumerator, which supports a simple iteration over a non-generic
  collection.
---

# IEnumerable and IEnumerator Interfaces

## IEnumerable Interface

IEnumerable is the base interface of all collection classes as shown below.

![](../../.gitbook/assets/image%20%285%29.png)

All classes implemented IEnumerable can be looped using foreach:

```csharp
IEnumerable<int> result = from value in Enumerable.Range(0, 2)
                                  select value;
foreach (int value in result)
{
   Console.WriteLine(value);
}
```

## IEnumerator Interface

### Properties  <a id="properties"></a>

| [Current](https://docs.microsoft.com/en-us/dotnet/api/system.collections.ienumerator.current?view=netframework-4.7.2#System_Collections_IEnumerator_Current) | Gets the element in the collection at the current position of the enumerator. |
| :--- | :--- |


### Methods  <a id="methods"></a>

| [MoveNext\(\)](https://docs.microsoft.com/en-us/dotnet/api/system.collections.ienumerator.movenext?view=netframework-4.7.2#System_Collections_IEnumerator_MoveNext) | Advances the enumerator to the next element of the collection. |
| :--- | :--- |
| [Reset\(\)](https://docs.microsoft.com/en-us/dotnet/api/system.collections.ienumerator.reset?view=netframework-4.7.2#System_Collections_IEnumerator_Reset) | Sets the enumerator to its initial position, which is before the first element in the collection. |

## Example of implementing IEnumberable

```csharp
using System;
using System.Collections;

// Simple business object.
public class Person
{
    public Person(string fName, string lName)
    {
        this.firstName = fName;
        this.lastName = lName;
    }

    public string firstName;
    public string lastName;
}

// Collection of Person objects. This class
// implements IEnumerable so that it can be used
// with ForEach syntax.
public class People : IEnumerable
{
    private Person[] _people;
    public People(Person[] pArray)
    {
        _people = new Person[pArray.Length];

        for (int i = 0; i < pArray.Length; i++)
        {
            _people[i] = pArray[i];
        }
    }

// Implementation for the GetEnumerator method.
    IEnumerator IEnumerable.GetEnumerator()
    {
       return (IEnumerator) GetEnumerator();
    }

    public PeopleEnum GetEnumerator()
    {
        return new PeopleEnum(_people);
    }
}

// When you implement IEnumerable, you must also implement IEnumerator.
public class PeopleEnum : IEnumerator
{
    public Person[] _people;

    // Enumerators are positioned before the first element
    // until the first MoveNext() call.
    int position = -1;

    public PeopleEnum(Person[] list)
    {
        _people = list;
    }

    public bool MoveNext()
    {
        position++;
        return (position < _people.Length);
    }

    public void Reset()
    {
        position = -1;
    }

    object IEnumerator.Current
    {
        get
        {
            return Current;
        }
    }

    public Person Current
    {
        get
        {
            try
            {
                return _people[position];
            }
            catch (IndexOutOfRangeException)
            {
                throw new InvalidOperationException();
            }
        }
    }
}

class App
{
    static void Main()
    {
        Person[] peopleArray = new Person[3]
        {
            new Person("John", "Smith"),
            new Person("Jim", "Johnson"),
            new Person("Sue", "Rabon"),
        };

        People peopleList = new People(peopleArray);
        foreach (Person p in peopleList)
            Console.WriteLine(p.firstName + " " + p.lastName);

    }
}
```


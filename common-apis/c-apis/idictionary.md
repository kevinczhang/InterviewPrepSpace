---
description: Represents a nongeneric collection of key/value pairs.
---

# IDictionary

The [IDictionary](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary?view=netcore-2.2) interface is the base interface for nongeneric collections of key/value pairs. For the generic version of this interface, see [System.Collections.Generic.IDictionary&lt;TKey,TValue&gt;](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.idictionary-2?view=netcore-2.2).

Each element is a key/value pair stored in a [DictionaryEntry](https://docs.microsoft.com/en-us/dotnet/api/system.collections.dictionaryentry?view=netcore-2.2) object.

```csharp
class Program
{
    static void Main()
    {
        // Example Dictionary again.
        Dictionary<string, int> d = new Dictionary<string, int>()
        {
            {"cat", 2},
            {"dog", 1},
            {"llama", 0},
            {"iguana", -1}
        };
        // Loop over pairs with foreach.
        foreach (KeyValuePair<string, int> pair in d)
        {
            Console.WriteLine("{0}, {1}", pair.Key, pair.Value);
        }
        // Use var keyword to enumerate dictionary.
        foreach (var pair in d)
        {
            Console.WriteLine("{0}, {1}", pair.Key, pair.Value);
        }
    }
}
```

### Properties  <a id="properties"></a>

| [IsFixedSize](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary.isfixedsize?view=netcore-2.2#System_Collections_IDictionary_IsFixedSize) | Gets a value indicating whether the [IDictionary](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary?view=netcore-2.2) object has a fixed size. |
| :--- | :--- |
| [IsReadOnly](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary.isreadonly?view=netcore-2.2#System_Collections_IDictionary_IsReadOnly) | Gets a value indicating whether the [IDictionary](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary?view=netcore-2.2) object is read-only. |
| [Item\[Object\]](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary.item?view=netcore-2.2#System_Collections_IDictionary_Item_System_Object_) | Gets or sets the element with the specified key. |
| [Keys](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary.keys?view=netcore-2.2#System_Collections_IDictionary_Keys) | Gets an [ICollection](https://docs.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=netcore-2.2) object containing the keys of the [IDictionary](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary?view=netcore-2.2) object. |
| [Values](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary.values?view=netcore-2.2#System_Collections_IDictionary_Values) | Gets an [ICollection](https://docs.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=netcore-2.2) object containing the values in the [IDictionary](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary?view=netcore-2.2) object. |

### Methods  <a id="methods"></a>

| [Add\(Object, Object\)](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary.add?view=netcore-2.2#System_Collections_IDictionary_Add_System_Object_System_Object_) | Adds an element with the provided key and value to the [IDictionary](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary?view=netcore-2.2) object. |
| :--- | :--- |
| [Clear\(\)](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary.clear?view=netcore-2.2#System_Collections_IDictionary_Clear) | Removes all elements from the [IDictionary](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary?view=netcore-2.2) object. |
| [Contains\(Object\)](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary.contains?view=netcore-2.2#System_Collections_IDictionary_Contains_System_Object_) | Determines whether the [IDictionary](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary?view=netcore-2.2) object contains an element with the specified key. |
| [GetEnumerator\(\)](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary.getenumerator?view=netcore-2.2#System_Collections_IDictionary_GetEnumerator) | Returns an [IDictionaryEnumerator](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionaryenumerator?view=netcore-2.2) object for the [IDictionary](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary?view=netcore-2.2) object. |
| [Remove\(Object\)](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary.remove?view=netcore-2.2#System_Collections_IDictionary_Remove_System_Object_) | Removes the element with the specified key from the [IDictionary](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary?view=netcore-2.2) object. |

```csharp
class Program
{
    static void Main()
    {
        var values = new Dictionary<string, string>();
        values.Add("A", "uppercase letter A");
        values.Add("c", "lowercase letter C");

        // Use inline "out string" with TryGetValue.
        if (values.TryGetValue("c", out string description))
        {
            System.Console.WriteLine(description);
        }
        
        // See whether Dictionary contains this string.
        if (values.ContainsKey("apple"))
        {
            int value = values["apple"];
            Console.WriteLine(value);
        }
    }
}
```


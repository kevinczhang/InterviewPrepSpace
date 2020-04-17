# String methods

## Most commonly used:

```csharp
string testStr = "test";
int strLen = testStr.Count();
bool strCompare = "".Equals(testStr);
bool strompare2 = "test".Equals(testStr, StringComparison.OrdinalIgnoreCase);
testStr = testStr.Trim();
bool strStartWith = testStr.StartsWith("a");
bool strEndWith = testStr.EndsWith("b");
string lowerCaseStr = testStr.ToLower();
string upperCaseStr = testStr.ToUpper();
string covertToString = 1234.ToString();
char c = testStr[0];

var chars = from str in testStr
            orderby c descending
            where c < 2
            select c;
Char.IsDigit(c);
Char.IsLetter(c);
Char.IsLetterOrDigit(c);
Char.IsLower(c);
Char.IsUpper(c);
Char.IsWhiteSpace(c);
Char.ToLower(c);
Char.ToUpper(c);
// String compare
"a".CompareTo("b");// return -1
"b".CompareTo("a");// return 1
```

## Replace and split methods

1.  [Split\(Char\[\]\)](https://docs.microsoft.com/en-us/dotnet/api/system.string.split?view=netcore-2.2#System_String_Split_System_Char___):  Splits a string into substrings that are based on the characters in an array.
2.  [Replace\(Char, Char\)](https://docs.microsoft.com/en-us/dotnet/api/system.string.replace?view=netcore-2.2#System_String_Replace_System_Char_System_Char_):  Returns a new string in which all occurrences of a specified Unicode character in this instance are replaced with another specified Unicode character.
3.  [Replace\(String, String\)](https://docs.microsoft.com/en-us/dotnet/api/system.string.replace?view=netcore-2.2#System_String_Replace_System_String_System_String_):  Returns a new string in which all occurrences of a specified string in the current instance are replaced with another specified string.
4.  [Replace\(String, String, StringComparison\)](https://docs.microsoft.com/en-us/dotnet/api/system.string.replace?view=netcore-2.2#System_String_Replace_System_String_System_String_System_StringComparison_)
5.  [Join\(String or char, String\[\]\)](https://docs.microsoft.com/en-us/dotnet/api/system.string.join?view=netcore-2.2#System_String_Join_System_String_System_String___):  Concatenates all the elements of a string array, using the specified separator between each element.
6.  [Join\(String, IEnumerable&lt;String&gt;\)](https://docs.microsoft.com/en-us/dotnet/api/system.string.join?view=netcore-2.2#System_String_Join_System_String_System_Collections_Generic_IEnumerable_System_String__):  Concatenates the members of a constructed [IEnumerable&lt;T&gt;](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.ienumerable-1?view=netcore-2.2) collection of type [String](https://docs.microsoft.com/en-us/dotnet/api/system.string?view=netcore-2.2), using the specified separator between each member.

```csharp
string data = "there is a/cat";
string[] words = data.Split(new char[] { ' ', '/' }, StringSplitOptions.RemoveEmptyEntries);
string sentence = "10 cats, 20 dogs, 40 fish and 1 programmer.";
string[] digits = Regex.Split(sentence, @"\D+"); // Get all digit sequence as strings.
string[] operands = Regex.Split(operation, @"\s+"); // Split it on whitespace sequences.
string[] uppercaseWords = Regex.Split(sentence, @"\W"); // Get all words.

string[] arr = { "one", "two", "three" };
string.Join(",", arr)
```

## StringBuilder methods

### Constructors  <a id="constructors"></a>

| [StringBuilder\(\)](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.-ctor?view=netcore-2.2#System_Text_StringBuilder__ctor) | Initializes a new instance of the [StringBuilder](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder?view=netcore-2.2) class. |
| :--- | :--- |
| [StringBuilder\(Int32\)](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.-ctor?view=netcore-2.2#System_Text_StringBuilder__ctor_System_Int32_) | Initializes a new instance of the [StringBuilder](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder?view=netcore-2.2) class using the specified capacity. |
| [StringBuilder\(String\)](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.-ctor?view=netcore-2.2#System_Text_StringBuilder__ctor_System_String_) | Initializes a new instance of the [StringBuilder](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder?view=netcore-2.2) class using the specified string. |

### Properties <a id="properties"></a>

| [Chars\[Int32\]](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.chars?view=netcore-2.2#System_Text_StringBuilder_Chars_System_Int32_) | Gets or sets the character at the specified character position in this instance. |
| :--- | :--- |
| [Length](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.length?view=netcore-2.2#System_Text_StringBuilder_Length) | Gets or sets the length of the current [StringBuilder](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder?view=netcore-2.2) object. |

#### Methods

| [Append\(Object\)](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.append?view=netcore-2.2#System_Text_StringBuilder_Append_System_Object_) | Appends the string representation of a specified object to this instance. |
| :--- | :--- |
| [Clear\(\)](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.clear?view=netcore-2.2#System_Text_StringBuilder_Clear) | Removes all characters from the current [StringBuilder](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder?view=netcore-2.2) instance. |
| [Insert\(Int32, Object\)](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.insert?view=netcore-2.2#System_Text_StringBuilder_Insert_System_Int32_System_Object_) | Inserts the string representation of an object into this instance at the specified character position. |
| [Remove\(Int32, Int32\)](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.remove?view=netcore-2.2#System_Text_StringBuilder_Remove_System_Int32_System_Int32_) | Removes the specified range of characters from this instance. |
| [Replace\(Char, Char\)](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.replace?view=netcore-2.2#System_Text_StringBuilder_Replace_System_Char_System_Char_) | Replaces all occurrences of a specified character in this instance with another specified character. |
| [ToString\(\)](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.tostring?view=netcore-2.2#System_Text_StringBuilder_ToString) | Converts the value of this instance to a [String](https://docs.microsoft.com/en-us/dotnet/api/system.string?view=netcore-2.2). |




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




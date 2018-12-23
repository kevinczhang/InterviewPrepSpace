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
```


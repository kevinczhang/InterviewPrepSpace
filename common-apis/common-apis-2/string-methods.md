# String methods

### Most commonly used:

```java
String str = "test";
int strLen = testStr.length();
boolean strCompare = "".equals(testStr);
boolean strCompare2 = "abc".equalsIgnoreCase(testStr);
// char in str
char[] strChars = testStr.toCharArray();
char strChar = testStr.charAt(0);
```

#### Compares two strings lexicographically:

1. The value 0 if the argument string is equal tothis string; 
2. A value less than 0 if this string is lexicographically less than the string argument;
3. A value greater than 0 if this string is lexicographically greater than the string argument.

```java
int StrCompareTo = "".compareTo(testStr);
```

### Replace and split methods

1.  [`replace`](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#replace-char-char-)`(char oldChar, char newChar);`Returns a string resulting from replacing all occurrences of `oldChar` in this string with `newChar`.
2.  [`replaceAll`](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#replaceAll-java.lang.String-java.lang.String-)`(`[`String`](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html) `regex,` [`String`](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html) `replacement);`Replaces each substring of this string that matches the given [regular expression](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html#sum) with the given replacement.
3.  [`replaceFirst`](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#replaceFirst-java.lang.String-java.lang.String-)`(`[`String`](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html) `regex,` [`String`](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html) `replacement);`Replaces the first substring of this string that matches the given [regular expression](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html#sum) with the given replacement.
4.  [`split`](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#split-java.lang.String-)`(`[`String`](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html) `regex);`Splits this string around matches of the given [regular expression](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html#sum).

```java
// Split on comma or colon.
String[] parts = testStr.split("[,:]");
// Split on 1+ non-word characters.
String[] words1 = testStr.split("\\W+");
// Separate based on number delimiters.
String[] words2 = testStr.split("\\d+");
// Separate by spaces or , with spaces or . With spaces
String str = "a d, m, i.n";
String delimiters = "\\s+|,\\s*|\\.\\s*";
String[] tokensVal = str.split(delimiters);
// Remove '(' or ')'
String temp = testStr.replaceAll("[()]", "");
```


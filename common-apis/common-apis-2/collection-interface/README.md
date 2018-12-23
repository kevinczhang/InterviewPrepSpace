---
description: Basic concepts about Collection interface and Collections
---

# Collection Interface

## Collection Interface

```java
public interface Collection extends Iterable
```

### Iterable Interface

Available methods: hasNext, next, remove

```java
List<String> nameList = new ArrayList<>();
Iterator<String> itr = nameList.iterator();
while(itr.hasNext()) {
	itr.next();
	// Must call next before remove
	itr.remove();
}
```

### Collection subInterfaces and methods

1. Commonly used subInterfaces: [List](https://interviewprepspace.gitbook.io/project/~/edit/drafts/-LUNMZGQAZaD5Ap8yYw1/common-apis/common-apis-2/collection-interface/list-interface), [Queue](https://interviewprepspace.gitbook.io/project/~/edit/drafts/-LUNMZGQAZaD5Ap8yYw1/common-apis/common-apis-2/collection-interface/queue-interface) and Set
2.  [`add`](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html#add-E-)`(`[`E`](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html) `e);`Ensures that this collection contains the specified element \(optional operation\).
3.  [`addAll`](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html#addAll-java.util.Collection-)`(`[`Collection`](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)`<? extends` [`E`](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)`> c);`Adds all of the elements in the specified collection to this collection \(optional operation\).
4.  [`clear`](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html#clear--)`();`Removes all of the elements from this collection \(optional operation\).
5.  [`contains`](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html#contains-java.lang.Object-)`(`[`Object`](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html) `o);`Returns true if this collection contains the specified element.
6.  [`containsAll`](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html#containsAll-java.util.Collection-)`(`[`Collection`](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)`<?> c);`Returns true if this collection contains all of the elements in the specified collection.
7.  [`remove`](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html#remove-java.lang.Object-)`(`[`Object`](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html) `o);`Removes a single instance of the specified element from this collection, if it is present \(optional operation\).
8.  [`removeAll`](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html#removeAll-java.util.Collection-)`(`[`Collection`](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)`<?> c);`Removes all of this collection's elements that are also contained in the specified collection \(optional operation\).
9.  [`removeIf`](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html#removeIf-java.util.function.Predicate-)`(`[`Predicate`](https://docs.oracle.com/javase/8/docs/api/java/util/function/Predicate.html)`<? super` [`E`](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)`> filter);`Removes all of the elements of this collection that satisfy the given predicate.
10.  [`size`](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html#size--)`();`Returns the number of elements in this collection.
11.  [`toArray`](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html#toArray--)`();`Returns an array containing all of the elements in this collection.
12.  [`isEmpty`](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html#isEmpty--)`();`Returns true if this collection contains no elements.

## Interface List&lt;E&gt; 



1. 

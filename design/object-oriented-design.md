# Object Oriented Design

Object-oriented design questions require a candidate to sketch out the classes and methods to implement technical problems or real-life objects.

## How to Approach

### Step 1: Handle Ambiguity

Object-oriented design \(OOD\) questions are often intentionally vague in order to test whether you'll make assumptions or if you'll ask clarifying questions.

### Step 2: Define the Core Objects

Now that we understand what we're designing, we should consider what the "core objects" in a system are.

### Step 3: Analyze Relationships

Having more or less decided on our core objects, we now want to analyze the relationships between the objects.

### Step 4: Investigate Actions

At this point, you should have the basic outline of your object-oriented design. What remains is to consider the key actions that the objects will take and how they relate to each other.

## Design Patterns

It is used to control the number of objects created by preventing external instantiation and modification.

This concept can be generalized to systems that operate more efficiently when only one object exists, or that restrict the instantiation to a certain number of objects, such as:

1. private constructor - no other class can instantiate a new object.
2. private reference - no external modification.
3. public static method is the only place that can get an object.

### Singleton Class

Eager Mode:

```java
public final class AmericaPresident {
	private static final AmericaPresident thePresident = new AmericaPresident();
 
	private AmericaPresident() {}
 
	public static AmericaPresident getPresident() {
		return thePresident;
	}
}
```

Lazy Mode:

```java
public final class AmericaPresident {
	private static AmericaPresident thePresident;
 
	private AmericaPresident() {}
 
	public static AmericaPresident getPresident() {
		if (thePresident == null) {
			thePresident = new AmericaPresident();
		}
		return thePresident;
	}
}
```

### Factory Method

Factory design pattern is used for creating an object based on different parameters. The example below is about creating human in a factory.

```java
interface Human {
	public void Talk();
	public void Walk();
}
 
 
class Boy implements Human{
	@Override
	public void Talk() {
		System.out.println("Boy is talking...");		
	}
 
	@Override
	public void Walk() {
		System.out.println("Boy is walking...");
	}
}
 
class Girl implements Human{
 
	@Override
	public void Talk() {
		System.out.println("Girl is talking...");	
	}
 
	@Override
	public void Walk() {
		System.out.println("Girl is walking...");
	}
}
 
public class HumanFactory {
	public static Human createHuman(String m){
		Human p = null;
		if(m.equals("boy")){
			p = new Boy();
		}else if(m.equals("girl")){
			p = new Girl();
		}
 
		return p;
	}
}
```


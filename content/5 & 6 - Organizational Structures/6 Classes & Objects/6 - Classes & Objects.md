# Object Oriented Programming
![[Untitled design (7).png]]
## Syntax
```java
// CLASS
public class Name{
	//code
}

// Object
className objectName = new className();
```

So, at some point in this course, you might've asked yourself: *What is Object-Oriented Programming?* Well, since you stayed here for so long I might as well tell you!

🌟 **Object-Oriented Programming** is (generally) the mindset that everything stems from *a blueprint/general idea (**Class)***  and from there we create *objects with specific details (**Object**)*. In philosophy, we call this a ***deductive** mindset.*

It's a little weird to understand so I like to think of it in this way:
> Everyone has an idea of a person, we know that they **generally** have a *name, age, and nationality.* 
> 
> Now what if we must create an actual person! Based on the **general properties of *our idea of a person*,** we must provide ***specific details*** such as their actual name (Cameron Winters), actual age (27), and actual nationality (American). 
>  
> Now create **another** unique person, based on the general details of the *our properties of a person*, we must provide *specific details* such as their actual name (Emily Greene), actual age (26), and actual nationality (Italian).
> 
> As you may notice, both Cameron and Emily **derive from the general idea (Class) but are two different people (Objects / Instances of an Object)**

*This entire concept is an entire can of worms, and thus this will really only serve as an incredibly basic introduction to the concept of OOP (Specifically only [[6 - Classes & Objects]]). If you're a total beginner, don't worry about this all that much; it's an organizational mindset that comes in handy when creating bigger or more complex programs.*
# Class
## Syntax
```java
public class Name{
	//code
}
```

A **class** is often described as the **blueprint**, and that definition is totally fine, but it's better to think of it essentially as the 🌟 **general idea / concept of something**.
```java
	public class Person{
		String name;
		int age;
		String race;
		void sayName(){
			System.out.println("Hi! My name is " + name);
		}
}
```
We all have a basic idea of a person; but when you look at everyone around you, you notice that everyone has different names, different ages, different races, etc. The one thing that unites everyone *conceptually* is that we all have the same general details (names, ages, races, etc)

Generally, it's best practice to  have 🌟 **each class be its own file**. We will be having to immediately break standard practices for the sake of *simplicity.* For now, **simply create your class outside of the public class Main() block**

```java
class Person {
    int age;
    String name;
    String race;

    void sayName() {
        System.out.println("Hi! My name is " + name);
    }
}
public class Main {
    public static void main(String[] args) {
		// MORE STUFF HERE LATER!!
    }
}
```

Now that we built out the basic idea of the person, lets go build one!
# Objects / Instantiate
## Syntax
```java
className objectName = new className();
```

An **object** is often described as the **product of the blueprint**, and that definition is totally fine, but it's also to think of it essentially as the **specific realization of an object**.
```java
public class Main {
    public static void main(String[] args) {

        Person brooke = new Person();
        Person martin = new Person();
    }
}
```
*brooke* and *martin* are two different **instances** of **the same general idea** 

From there, we can assign them traits and make them act uniquely from each other. 
```java
class Person {
    int age;
    String name;
    String race;

    void sayName() {
        System.out.println("Hi! My name is " + name);
    }
}

public class Main {
    public static void main(String[] args) {

        Person brooke = new Person();
        Person martin = new Person();

        brooke.age = 17;
        brooke.name = "Brooke";
        brooke.race = "Filipino";

        martin.age = 16;
        martin.name = "Martin";
        martin.race = "Korean";

        brooke.sayName();
        martin.sayName();
    }
}
```

You might ask: Why do we need `new` in `className objectName = new className();`?

To put simply, `new` is just a way to tell Java: *"Create a new copy of the `className` in memory!"* and *"assign that new copy to the variable `objectName`"*

In our case, writing `Person brooke;` only creates a name tag (or a reference variable) and *it doesn't create an actual person yet.* Because `new` is called twice, once for `brooke` and once for `martin`, **we get two different people.** *(Java gives each of them their own separate space in the memory.)*

So evn though they share the exact same blueprint which is `Person`, whatever values you store in `brooke` *(e.g. brooke.age = 17)* won't affect `martin` and vice versa.

## Modifiers
Now, if you recall the lesson from [[5.3 - Access & Non-Access Modifiers]], you'll know the concept of *modifiers* and those same modifiers apply too! Though again, just like in the lesson, you really must only *start* with like **3**: 

| Access Modifier    | Meaning                                                                                                                                                        | Example                       |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------- |
| `public`           | Can be accessed from anywhere (most notably **outside of the file**)                                                                                           | `public void sayHello() { }`  |
| `private`          | Can only be accessed within its own class (for now, it means that it can only be accessed only **within** the file)                                            | `private void sayHello() { }` |
| ` `_(no modifier)_ | Literally nothing, it can **only be access within the same package** (think of it as it can be accessed by all other files within the same folder in your IDE) | `void sayHello() { }`         |
## Moving Forward: [[7 - Programming Mindsets & Tips(Optional)]]
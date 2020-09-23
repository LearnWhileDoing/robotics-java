---
description: 'Peek-a-boo, I see you!'
---

# Scope

In most programming languages, a concept called _scope_ limits how your program has access to different variables \(and sometimes methods, but not in Java\). Let's look at the following example:

```java
// please don't use this tutorial as baking advice :)
class CakeRecipe {
    public void prepareIngredients() {
        double sugar = 1;
        double butter = 0.5;
        double eggs = 2;
        double flour = 1.5;
    }
    
    public double mix() {
    }
    
    public void bake(double mixture) {
        /* bake a cake */
    }
}
```

In this code example, we are simulating baking a cake. We have all of the ingredients prepared, so now we need to mix the ingredients. Simple, right?

```java
public double mix() {
    return sugar + butter + eggs + flour;
}
```

Well, not quite. This code will give us an error. Why? The ingredient variables are _out of scope_. This means that the ingredient variables are _scoped_ to the `prepareIngredients()` method, and are unavailable to the `mix()` method. How can we fix this? 

We can use instance variables. All instance variables are available within their class, and to all of the methods. Let's rewrite the `CakeRecipe` class, now with instance variables.

```java
class CakeRecipe {
    double sugar;
    double butter;
    double eggs;
    double flour;
    
    public void prepareIngredients() {
        sugar = 1;
        butter = 0.5;
        eggs = 2;
        flour = 1.5;
    }
    
    public double mix() {
        return sugar + butter + eggs + flour;
    }
    
    public Cake bake(double mixture) {
        /* bake a cake */
    }
}
```

Great! We now can use the variables anywhere within this class because it is _in scope_.


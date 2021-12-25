# Lambdas and functional interfaces

## Basic lambda syntax

```java
// Compact syntax
a -> a.isAlive()

// Full syntax
(Animal a) -> {
    return a.isAlive();
}
```

## Basic functional interfaces

### [Predicate](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/function/Predicate.html)

```java
public interface Predicate<T> {
    boolean test(T t);
}
```

### [Consumer](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/function/Consumer.html)

```java
public interface Consumer<T> {
    void accept(T t);
}
```

### [Supplier](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/function/Supplier.html)

```java
public interface Supplier<T> {
    T get();
}
```

### [Comparator](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/Comparator.html)

```java
public interface Comparator<T> {
    int compare(T o1, T o2);
}
```

## Variables referenced from the lambda body

* Instance variables are always allowed
* Class variables are always allowed
* Method parameters and local variables are allowed only if they are `final` or *effectively final*

| Variable type     | Rule                         |
|-------------------|------------------------------|
| Instance variable | Allowed                      |
| Static variable   | Allowed                      |
| Local variable    | Allowed if effectively final |
| Method parameter  | Allowed if effectively final |
| Lambda parameter  | Allowed                      |

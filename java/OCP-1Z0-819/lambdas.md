# Lambdas

## Funtional interfaces

Is an interface with a single abstract method wich you can implement with a lambda expression. They can be marked using the [@FuntionalInterface](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/FunctionalInterface.html) annotation. The methods inherit from other sources does not count as methods to be implemented. The same applies for static methods.

## Common standard functional interfaces

- [Function](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/function/Function.html)
- [Consumer](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/function/Consumer.html)
- [Supplier](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/function/Supplier.html)
- [Predicate](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/function/Predicate.html)
- [UnaryOperator](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/function/UnaryOperator.html)
- [BiFunction](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/function/BiFunction.html)
- [BiConsumer](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/function/BiConsumer.html)
- [BiPredicate](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/function/BiPredicate.html)
- [BinaryOperator](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/function/BinaryOperator.html)

## Specialized standard functional interfaces

There are multiple specializations for this kind of interface. For complete refrence check this [link](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/function/package-summary.html)

## Lambda expressions

### General syntax

```java
// no parameters
() -> System.out.Println("Hello world")

// single parameter
file -> file.isHidden()

// two or more parameters
(p1, p2) -> p1.getPrice().compareTo(p2.getPrice())

// lambda with code block
(p1, p2) -> {
    p1.setPrice(p1.getPrice() * 0.75)
    p1.getPrice().compareTo(p2.getPrice())
}
```

### Variable capturing

To use an external variable in a labmda expression, this must be final or effectively final. Also, you cannot modify a captured variable inside a lambda expression but you can modify its state

> As a good practice, you should avoid variable side-effects in lambda expressions

### Exceptions inside a lambda expression

You cannot throw any exception in lamda expressions. That's is because lambda expression must follow the contract defined by their interfaces and those interfaces does not define any exception

### Method references

The method must match the signature of the lambda expression used. In this case is [Predicate](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/function/Predicate.html) and [Consumer](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/function/Consumer.html)

```java
List<Product> products = ExampleData.getProducts();

products.removeIf(ProductUtils::isExpensive)
products.forEach(System.out::println);
```

# Operators

---

## Types of operators

* Unary
* Binary
* Ternary

## Operator precedence

| Operator                          | Example                                            |
|-----------------------------------|----------------------------------------------------|
| Parentheses                       | (expresssion)                                      |
| Post-unary                        | expression++, expression--                         |
| Pre-unary                         | ++ expression, --expression                        |
| Other                             | -, !, ~, +, (type)                                 |
| Multiplication, division, modulus | *, /, %                                            |
| Addition, subtraction             | +, -                                               |
| Bit level shifting                | <<, >>, >>>                                        |
| Relational                        | <, >, <=, >=, `instanceof`                         |
| Equal to, not equal to            | ==, !=                                             |
| Logical                           | &, ^, \|                                           |
| Short-circuit                     | &&, \|\|                                           |
| Ternary                           | boolean expression ? expression1 : expression2     |
| Assignment                        | =, +=, -=, *=, /=, %=, &=, ^=, \|=, <<=, >>=, >>>= |

## Numeric promotion

### Numeric promotion Rules

1. If two values have different data types, Java will automaticaly promote one of the values to the larger of the two data types.
2. If one of the values is integral and the other is floating-point, Java will automatically promote the integral value to the floating-point value's data type.
3. Smaller data types, namely, `byte`, `short`, and `char`, are first promoted to `int` any time ther're used with a Java binary arithemtic operator, even if neigher of the operands is `int`.
4. After all promotion has occurred and the operands have the same data type, the resulting value will have the same data type as its promoted operands.

## Casting values

Casting is optional when we want to convert to a *larger* data type and it is required when converting from a larger type to a smaller one

```java
float egg = 2.0 / 9; // Does not compile
float egg = (float) (2.0 / 9); // Explicit casting
```

When using compound operators, the operands are casted implicitly

```java
long goat = 10;
int sheep = 5;

sheep = sheep * goat; // Does not compile
sheep *= goat; // Compiles due to implicit casting
```

## Comparing values

There's a difference between *two objects are the same* and *two objects are equivalent*. That distinction does not exist for `numeric` and `boolean` values

When comparing two objects using the equality operator `==`, it will return `true` if, and only if both variables point to the same object or their values are `null`

## Logical operators

| Operator | Description                                                                    |
|----------|--------------------------------------------------------------------------------|
| &        | Logical `AND` is `true` only if both values are `true`                         |
| \|       | Inclusive `OR` is `true` if at least one of the values is `true`               |
| ^        | Exclusive `XOR` is `true` only if one value is `true` and the other is `false` |
| &&       | Short-circuit `AND`                                                            |
| \|\|     | Short-circuit `OR`                                                             |

## Avoiding a NullPointerException

```java
if (variable != null & variable.doSomething()) { // Could throw a NullPointerException
    // Do something
}

if (variable != null && variable.doSomething()) { // Short-circuit AND
    // Do something
}
```

## Making decisitions with the ternary operator

```java
booleanExpression ? valueReturnedWhenTrue : valueReturnedWhenFalse;
```

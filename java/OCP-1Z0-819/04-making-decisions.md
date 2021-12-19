# Making decisions

## Switch

It is compatible with the following data types: `byte`, `short`, `int`, `char`, `enum` and `String`.
It also works with the following wrappers: `Byte`, `Short`, `Integer`, `Character`.

## Labels

* Follow the same naming conventions as variables
* Usually they are named in capital case to improve readability

## Unreachable code

If a statement(s) is not reachable due to a previous `continue`, `break` or `return`, the code will no compile.

```java
int checkDate = 0;

while (checkDate < 10) {
    checkDate++;

    if (checkDate > 100) {
        break;
        checkDate++; // Does not compile
    }
}
```

```java
int minute = 1;

WATCH: while(minute > 2) {
    if(minute++ > 2) {
        continue WATCH;
        System.out.print(minute); // DOES NOT COMPILE
    }
}
```

```java
int hour = 2;

switch(hour) {
    case 1: return;
        hour++; // DOES NOT COMPILE
    case 2:
}
```

### Advanced flow control usage

|          | Labels | `break` | `continue` |
|----------|--------|---------|------------|
| while    | Yes    | Yes     | Yes        |
| do while | Yes    | Yes     | Yes        |
| for      | Yes    | Yes     | Yes        |
| switch   | Yes    | Yes     | No         |

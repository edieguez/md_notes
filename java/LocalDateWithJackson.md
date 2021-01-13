# Java 8 LocalDate Jackson format

```java
@JsonDeserialize(using = LocalDateDeserializer.class)  
@JsonSerialize(using = LocalDateSerializer.class)  
private LocalDate dateOfBirth;
```

## Reference
[stackoverflow](https://stackoverflow.com/questions/28802544/java-8-localdate-jackson-format)
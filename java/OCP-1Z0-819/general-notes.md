# General notes

## Compiling and running a Java program

When you compile a program, you must specify the extension. When you execute a class file, the extension must be excluded.

By default `javac` command places the compiled classes in the same directory as the source code. To specify a different directory use the `-d` option.
To add more classes to the classpath when you use the `java` command, add the `-cp $path` flag. It may point to a directory or a precompiled Java class file. `-classpath $path` and `--class-path $path` are also valid flags. If you specify more than one file/directory the separator is `:` for Linux/Mac and `;` for Windows. It also supports wildcards.

```bash
javac -d . -cp '.:classes:/opt/java/directoryWithJars/*' HelloWorld.java
java HelloWorld
```

## Creating a JAR file

```bash
jar -cvf newJarFile.jar .
jar --create --verbose --file newJarFile.jar -C directory .
```

* `-c`, `--create` Create a new JAR file
* `-v`, `--verbose` Prints dtauls when working with JAR files
* `-f <filename>` JAR filename
* `-C <directory>` Directory containing the files to be used to create the JAR

## Running a program in one line

In `Java 11` you can a file without compiling it first. It can only be used if your program has __only one__ file and only references classes supplied by the JDK

```bash
java HelloWorld.java
```

## Class declaration

```java
// The class name must be the same as the Java file.
// Only one public class is allowed per file
public class Animal {
    private String name;

    public Animal(String name) {
        this.name = name;
    }
}
```

## Automatic imports

All the content from [java.lang](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/package-summary.html) is imported automaticaly. The same applies to classes in the same package as the current class.

```java
// Only one wildcard can be used per import statement
import java.nio.*.*;

// Not valid. A wildcard only matches classes, not (no static) methods
import java.nio.file.Paths.*;
```

Is important to note that wildcards **only matches classes**. Subpackages will not be included

## Explicit imports

```java
import java.util.Date;

// This package also has a Date class
import java.sql.*;
```

If you have name collisions in your classes using a wildcard, Java will give precedence to the explicit imports

## Package creation

The default package is a special package without a name

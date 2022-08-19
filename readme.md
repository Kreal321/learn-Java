# Learning Java OCA Notes

## Comments
Multiline comment: anteater, elephant. 
Single line comment: bear, cat, dog. 
Compiler error: ferret

```Java

/*
* // anteater
*/

// bear

// // cat

// /* dog */

/* elephant */

/*
* /* ferret */
*/

```
Explanation: 

anteater is in a multiline comment. Everything between /*
and */ is part of a multiline comment—even if it includes a single-line comment within it! bear is your basic single-line comment. cat and dog are also single-line comments.

Everything from // to the end of the line is part of the comment, even if it is another type of comment. elephant is your basic multiline comment.
The line with ferret is interesting in that it doesn’t compile. Everything from the fi rst /* to the fi rst */ is part of the comment, which means the compiler sees something like this: /* */ */


## Package Declarations and Imports
Redundant Imports: three of the imports are redundant

```Java

import java.lang.System;
import java.lang.*;
import java.util.Random;
import java.util.*;

```

Naming Conflicts: The type Date is ambiguous

```Java
import java.util.*;
import java.sql.*; // DOES NOT COMPILE
```

Solution: If you explicitly import a class name, it takes precedence over any
wildcards present. 

```Java
import java.util.Date;
import java.sql.*;
```

## Constructors

```Java

public class Chicken {
    int numEggs = 0; // initialize on line
    String name;
    public Chicken() {
        name = "Duke"; // initialize in constructor
    } 
}

```
## Order of Initialization
Rules:
1. Fields and instance initializer blocks are run in the order in which they appear in the file.
2. The constructor runs after all fields and instance initializer blocks have run.

```Java

public class Chick {
    private String name = "Fluffy";

    { System.out.println("setting field"); }

    public Chick() {
        name = "Tiny";
        System.out.println("setting constructor");
    }

    public static void main(String[] args) {
        Chick chick = new Chick();
        System.out.println(chick.name); 
    } 
}

```
Output: setting field, setting constructor, Tiny

```Java

public class Egg {

    public Egg() {
        number = 5;
    }

    public static void main(String[] args) {
        Egg egg = new Egg();
        System.out.println(egg.number);
    }

    private int number = 3;
    { number = 4; } 

}
```
Output: 5

## Java primitive types
| Keyword | Type | Example |
| ----------- | ----------- | ----------- |
|boolean | true or false | true |
|byte | 8-bit integral value | 123 |
|short | 16-bit integral value | 123 |
|int | 32-bit integral value | 123 |
|long | 64-bit integral value | 123 |
|float | 32-bit floating-point value | 123.45f |
|double | 64-bit floating-point value | 123.456 |
|char | 16-bit Unicode value | 'a' |

## defining an int value with a literal
1. octal (digits 0–7), which uses the number 0 as a prefix—for example, 017
2. hexadecimal (digits 0–9 and letters A–F), which uses the number 0 followed by x or X
as a prefix—for example, 0xFF
3. binary (digits 0–1), which uses the number 0 followed by b or B as a prefix—for example,
0b10
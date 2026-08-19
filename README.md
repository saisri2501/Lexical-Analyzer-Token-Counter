# Lexical Analyzer & Token Counter

## 1. Title

**Lexical Analyzer & Token Counter**

## 2. Objective

The objective of this project is to develop a lexical analyzer in Java that reads a C source-code file, identifies different types of tokens, and counts the occurrences of each token type.

The analyzer identifies:

* Keywords
* Identifiers
* Operators
* Constants/Literals
* String Literals
* Separators/Delimiters
* Special Symbols
* Comments

## 3. Problem Statement

Develop a program that performs lexical analysis on a C source-code file.

The program reads the source code and classifies each token according to its type. It then displays the token, its corresponding type, and the total number of tokens belonging to each category.

The program should recognize keywords, identifiers, operators, constants/literals, separators/delimiters, special symbols, and comments.

## 4. Algorithm

1. Start the program.
2. Ask the user to enter the name of the C source-code file.
3. Open the file for reading.
4. Read the contents of the file.
5. Read the source code character by character.
6. Ignore whitespace characters.
7. Check whether the current characters form a single-line or multi-line comment.
8. Check whether the token is a keyword or identifier.
9. Check whether the token is a numeric constant.
10. Check whether the token is a string or character literal.
11. Check whether the character is a separator.
12. Check whether the character forms an operator.
13. Classify any remaining character as a special symbol.
14. Display each token along with its token type.
15. Increment the corresponding token counter.
16. Display the total count of each token category.
17. Close the file.
18. Stop the program.

## 5. Source Code

The project is implemented in Java using:

* `Scanner` for user input
* `FileReader` for reading the source file
* `BufferedReader` for efficient file reading
* Character checking methods for token identification
* String processing for identifying keywords and identifiers

The main source file is:

`LexicalAnalyzer.java`

## 6. Sample Input

The following C source code is used as sample input:

```c
int sum = a + b;
float average = sum / 2.0;

// Calculate average

if (average > 50)
    printf("Pass");
```

## 7. Sample Output

```text
TOKEN           TYPE
----------------------------------------
int             Keyword
sum             Identifier
=               Operator
a               Identifier
+               Operator
b               Identifier
;               Separator
float           Keyword
average         Identifier
=               Operator
sum             Identifier
/               Operator
2.0             Constant
;               Separator
//              Comment
if              Keyword
(               Separator
average         Identifier
>               Operator
50              Constant
)               Separator
printf          Identifier
(               Separator
"Pass"          String Literal
)               Separator
;               Separator
----------------------------------------

TOKEN COUNT
----------------------------------------
Keywords        : 3
Identifiers     : 7
Operators       : 4
Constants       : 2
String Literals : 1
Separators      : 8
Special Symbols : 0
Comments        : 1
```

## 8. Token Classification

| Token     | Token Type     |
| --------- | -------------- |
| `int`     | Keyword        |
| `sum`     | Identifier     |
| `=`       | Operator       |
| `a`       | Identifier     |
| `+`       | Operator       |
| `b`       | Identifier     |
| `;`       | Separator      |
| `float`   | Keyword        |
| `average` | Identifier     |
| `/`       | Operator       |
| `2.0`     | Constant       |
| `if`      | Keyword        |
| `(`       | Separator      |
| `>`       | Operator       |
| `50`      | Constant       |
| `)`       | Separator      |
| `printf`  | Identifier     |
| `"Pass"`  | String Literal |
| `//`      | Comment        |

### Token Categories

**Keywords**

Examples:

```text
int
float
if
```

**Identifiers**

Examples:

```text
sum
a
b
average
printf
```

**Operators**

Examples:

```text
=
+
/
>
```

The implementation also supports multi-character operators such as:

```text
==
!=
>=
<=
++
--
+=
-=
&&
||
```

**Constants**

Examples:

```text
50
2.0
```

**String Literals**

Example:

```text
"Pass"
```

**Separators**

Examples:

```text
(
)
;
{
}
[
]
,
```

**Comments**

Examples:

```text
// comment
```

and:

```text
/*
   comment
*/
```

**Special Symbols**

Characters that do not belong to the other recognized categories are classified as special symbols.

## 9. Test Cases

### Test Case 1 — Basic Declaration

```c
int x = 10;
float y = 20.5;
```

The program should identify keywords, identifiers, operators, constants, and separators.

### Test Case 2 — Conditional Statement

```c
if (x >= 10)
    x++;
else
    x--;
```

This tests keywords, identifiers, separators, constants, and multi-character operators.

### Test Case 3 — Comments

```c
// Single line comment

/*
   Multi-line comment
*/

int x = 10;
```

This tests both single-line and multi-line comments.

### Test Case 4 — String Literal

```c
printf("Hello World");
```

Expected token types include:

```text
printf          Identifier
(               Separator
"Hello World"   String Literal
)               Separator
;               Separator
```

### Test Case 5 — Multiple Operators

```c
a += 10;
b -= 5;
c == d;
x != y;
a && b;
a || b;
```

This tests multi-character operators.

## 10. Conclusion

The Java-based lexical analyzer successfully reads a C source-code file, identifies different types of tokens, classifies them, and counts the number of tokens in each category.

The project demonstrates the basic process of lexical analysis used in compiler design and provides token-level information from a source-code file.

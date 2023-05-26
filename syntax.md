
--------------------
Lexical structure
--------------------
Is the set of elementary rules that specifies how you write programs in that language.
--------------------
Case sensitive
--------------------
identifiers must always be typed with a consistent capitalization of letters.
```
The while keyword, for example, must be typed “while,” not “While” or “WHILE.” Similarly, online, Online, OnLine, and ONLINE are four distinct variable names.
```
--------------------
Charset
--------------------
JavaScript is case-sensitive and uses the Unicode character set. That means we can use unicode chars to define variables like ü:
const Früh = "foobar";
But, the variable früh is not the same as Früh because JavaScript is case sensitive.

In JavaScript, instructions are called statements and are separated by semicolons (;). A semicolon is not necessary after a statement if it is written on its own line. But if more than one statement on a line is desired, then they must be separated by semicolons.

--------------------
Literals
--------------------
A literal is a data value that appears directly in the code of a program.
```
"abc" --> string literal
123   --> number literal
2.4   --> number literal
5 + 5 --> an expressión, is not a literal, the literals will be the two fives
true  --> boolean literal
```

--------------------
Identifier
--------------------
Is simply a name to identify somthing, in javascript are used to name fucntions and variables. 

Must begin with a letter, an underscore (_), or a dollar sign ($)

--------------------
Reserved Words
--------------------
JavaScript reserves a number of identifiers as the keywords of the language itself.

Keep in mind that JavaScript implementations may define other global variables and functions.

--------------------
Semiclons
--------------------
JavaScript treats a line break as a semicolon if the next nonspace character cannot be interpreted as a continuation of the current statement.
```
var a 
a 
=
3
console.log(a)
```
JavaScript interprets this code like this; `var a; a = 3; console.log(a)`.
```
var y = x + f 
(a+b).toString()
```
`var y = x + f(a+b).toString();`

Exceptions:
- The return, break, and continue statements --> If a line break appears after any of these words, will always interpret that line break as a semicolon. 
```
return 
true;
```
`return; true;`
- ++ and −− operators --> If you want to use either of these operators as postfix operators, they must appear on the same line as the expression they apply to. Otherwise, the line break will be treated as a semicolon-
```
x
++
y
```
It is parsed as `x; ++y;`, not as `x++; y`.

--------------------
Basic concepts
--------------------
Statement --> is a line of code commanding a task.
Scope --> the scope is a proprety of the context and depend on his type of block (function, sample-block, global) will have one or more scopes in his context there are 6 types of scope. The scope of a variable is a component of the engine, the scope chain, and follows the following process (ChatGPT):
- The JavaScript engine starts by checking the current scope for the variable. If the variable is found in the current scope, it is considered declared and accessible.
- If the variable is not found in the current scope, the JavaScript engine moves to the next outer scope in the scope chain and repeats the process. It continues moving up the scope chain until it either finds the variable or reaches the global scope.
- If the JavaScript engine reaches the global scope and still doesn't find the variable, it determines that the variable has not been declared.
The scope is defined when the variable or block begin declared, not called in case of a function. The scope of a function will reach where is defined.

-------------------
What is JavaScript?
-------------------
- Is used for web applications with which you can interact directly without doing a page reload for every action. JavaScript is also used in more traditional websites to provide various forms of interactivity.
- JavaScript has almost nothing to do with the programming language named Java. The similar name was inspired by marketing.
- JavaScript is a high-level, often JavaScript engines are just-in-time compiled language that conforms to the ECMAScript standard. It has dynamic typing, prototype-based object-orientation, and first-class functions.
- The ECMAScript standard does not include any input/output (I/O), such as networking, storage, or graphics facilities. In practice, the web browser or other runtime system provides JavaScript APIs for I/O.
- JIT --> executing computer code that involves compilation during execution of a program (at run time) rather than before execution.

<img src="https://miro.medium.com/v2/resize:fit:1100/format:webp/1*ZIH_wjqDfZn6NRKsDi9mvA.png" width="600">

- When V8 compiles JavaScript code, the parser generates an abstract syntax tree. A syntax tree is a tree representation of the syntactic structure of the JavaScript code. Ignition, the interpreter, generates bytecode from this syntax tree. TurboFan, the optimizing compiler, eventually takes the bytecode and generates optimized machine code from it.


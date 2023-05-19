-------------------
What is JavaScript?
-------------------
- Is used for web applications with which you can interact directly without doing a page reload for every action. JavaScript is also used in more traditional websites to provide various forms of interactivity.
- JavaScript has almost nothing to do with the programming language named Java. The similar name was inspired by marketing.
- JavaScript is a high-level, often JavaScript engines are just-in-time compiled language that conforms to the ECMAScript standard. It has dynamic typing, prototype-based object-orientation, and first-class functions.
- The ECMAScript standard does not include any input/output (I/O), such as networking, storage, or graphics facilities. In practice, the web browser or other runtime system provides JavaScript APIs for I/O.
- Interpreter --> directly executes the source code of a program line by line. It reads each instruction, translates it into machine code or bytecode, and immediately executes it.
- JIT --> combines features of both interpreters and compilers. It dynamically compiles code during runtime, translating parts of the code into machine code or bytecode just before they are executed. The compiled code is then cached and reused for subsequent executions. Determines the most frequently used code and compiles it for better optimitzation.

<img src="https://miro.medium.com/v2/resize:fit:1100/format:webp/1*ZIH_wjqDfZn6NRKsDi9mvA.png" width="600">

- When V8 compiles JavaScript code, the parser generates an abstract syntax tree. A syntax tree is a tree representation of the syntactic structure of the JavaScript code. Ignition, the interpreter, generates bytecode from this syntax tree. TurboFan, the optimizing compiler, eventually takes the bytecode and generates optimized machine code from it.

-------------------
Dynamic Typing
-------------------
- Where the interpreter assigns variables a type at runtime based on the variable's value at the time.
- napi_value --> this is an opaque pointer that is used to represent a JavaScript value.

typedef struct {
  void* reserved;
} napi_value;

- A void pointer is a pointer that has no associated data type with it. A void pointer can hold address of any type and can be typecasted to any type. 


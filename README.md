-------------------
What is JavaScript?
-------------------
- Is used for web applications with which you can interact directly without doing a page reload for every action. JavaScript is also used in more traditional websites to provide various forms of interactivity.
- JavaScript has almost nothing to do with the programming language named Java. The similar name was inspired by marketing.
- JavaScript is a high-level, often JavaScript engines are just-in-time compiled language that conforms to the ECMAScript standard. It has dynamic typing, prototype-based object-orientation, and first-class functions.
- The ECMAScript standard does not include any input/output (I/O), such as networking, storage, or graphics facilities. In practice, the web browser or other runtime system provides JavaScript APIs for I/O.
-------------------
Understanding concepts
-------------------
- ECMAScript --> is the standard who defines the rules of how JavaScript works with the code. JavaScript uses the ECMAScript standard to undestenad the js code.
- Interpreter --> directly executes the source code of a program line by line. It reads each instruction, translates it into machine code or bytecode, and immediately executes it.
- JIT --> combines features of both interpreters and compilers. While is interpreting the code at the run time, it dynamically compiles code during runtime, translating parts of the code into machine code or bytecode just before they are executed. The compiled code is then cached and reused for subsequent executions. Determines the most frequently used code and compiles it for better optimitzation.
-------------------
V8 engine
-------------------
<img src="https://media.geeksforgeeks.org/wp-content/uploads/20191021114256/881.png" width="600">

<img src="https://marcradziwill.com/assets/images/blog/mastering-javascript-high-performance/V8-pipeline.jpg-800w.avif" width="600">

JavaScript engine converts your code into byte-code or optimized machine-code that runs on your device. The V8 engine has two main parts that play together in this process. As the V8 team choose car part names for the engine, it stuck with that by naming the subprocesses: Ignition and Turbofan.

When V8 compiles JavaScript code, the parser generates an abstract syntax tree. A syntax tree is a tree representation of the syntactic structure of the JavaScript code. Ignition, generates bytecode from the whole syntax tree, and starts interpreting the generated bytecode one by one, like interpreder does.

After that comes the Profiler; it will check for the repeating code that can be optimized from the interpreter. As soon as, it gets the repeating code, it basically moves the code into compiler (TurboFan).

TurboFan, the optimizing compiler, eventually takes the bytecode and generates optimized machine code from it. Turbofan is perfect for code after page load and frequently executed code. So the next time that the function begin called, it will skip the byte-code interpretation and inmidiatly execute the machine code generated by the compiler.

But as JavaScript is dynamic, we could call our function with a String instead of a Number. In this case, the optimistic assumption Turbofan made is wrong, and we have to go back to Ignitions execution (the code is de-optimized).

-------------------
Dynamic Typing
-------------------
- Where the interpreter assigns variables a type at runtime based on the variable's value at the time.
- napi_value --> this is an opaque pointer that is used to represent a JavaScript value.
```
typedef struct {
  void* reserved;
} napi_value;
```
- A void pointer is a pointer that has no associated data type with it. A void pointer can hold address of any type and can be typecasted to any type. 

-------------------
Object-Oriented language
-------------------
Programming --> are a way to classify programming languages based on their features. Languages can be classified into multiple paradigms.

OOPs refers to languages that use objects in programming. Object-oriented programming aims to implement real-world entities like inheritance, hiding, polymorphism, etc in programming. The main aim of OOP is to bind together the data and the functions that operate on them so that no other part of the code can access this data except that function.

OOPs Concepts:
- Class
- Objects
- Data Abstraction 
- Encapsulation
- Inheritance
- Polymorphism
- Dynamic Binding
- Message Passing

Inheritance --> focuses on the hierarchy and code reuse aspect by allowing subclasses to inherit properties and behaviors from a superclass. 
```
class Animal {
  constructor(name) {
    this.name = name;
  }

  eat() {
    console.log(`${this.name} is eating.`);
  }
}

class Dog extends Animal {
  bark() {
    console.log(`${this.name} is barking.`);
  }
}
```
Polymorphism --> allows objects of different classes to be treated as objects of a common superclass or interface.
```
class Shape {
  constructor() {
    this.name = "Shape";
  }

  draw() {
    console.log("Drawing a generic shape.");
  }
}

class Circle extends Shape {
  constructor() {
    super();
    this.name = "Circle";
  }

  draw() {
    console.log("Drawing a circle.");
  }
}
```

Imperative programming focuses on specifying instructions and controlling the flow of execution, while OOP focuses on modeling the problem domain using objects and their interactions.

Prototype-based programming is a style of object-oriented programming in which behaviour reuse (known as inheritance) is performed via a process of reusing existing objects that serve as prototypes. 

First-class citizensis --> an entity which supports all the operations generally available to other entities. 

First-class functions --> if it treats functions as first-class citizens. This means the language supports passing functions as arguments to other functions, returning them as the values from other functions, and assigning them to variables or storing them in data structures.

----------------
Basic Concepts
----------------
Primitive --> (primitive value, primitive data type) is data that is not an object and has no methods or properties.

JavaScript is case-sensitive and uses the Unicode character set. That means we can use unicode chars to define variables like `ü`:
```
const Früh = "foobar";
```

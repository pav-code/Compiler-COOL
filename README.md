# C++ Compiler for COOL
Compiler for COOL Language. Language features:  
+ Classes/Objects
+ Inheritance
+ Strong static-typed
+ Built-in Types
+ Expressions
+ Operational Semantics
+ Small Standard Library

Factorial in COOL:
```
class Main inherits IO {
  main(): Object {{
    out_string("Enter an integer greater-than or equal-to 0: ");

    let input: Int <- in_int() in
      if input < 0 then
        out_string("ERROR: Number must be greater-than or equal-to 0\n")
      else {
        out_string("The factorial of ").out_int(input);
        out_string(" is ").out_int(factorial(input));
        out_string("\n");
      }
      fi;
  }};

  factorial(num: Int): Int {
    if num = 0 then 1 else num * factorial(num - 1) fi
  };
};
```

# Setup Tools Environment 
+ Flex, Bison and Make <br/>
`sudo apt-get install flex-old bison build-essential csh libxaw7-dev`

+ To have the same environment as the Stanford CS143 Class<br/>
`sudo mkdir /usr/class`<br/>
`sudo chown $USER /usr/class`<br/>
`cp ./CompilerTools/student-dist.tar.gz /usr/class`<br/>
`cd /usr/class`<br/>
`tar -xf student-dist.tar.gz`<br/>

+ In the terminal that will be used to compile the Lexer, Parser, Semantic analyzer and Code generator<br/>
`PATH=/usr/class/cs143/cool/bin:$PATH`

# Lexer
+ Lexical specification file:<br/>
`cool.flex`
+ Run Flex to generate cool-lex.cc and use the Makefile to compile the Lexer binary:<br/>
`make -f /usr/class/cs143/assignments/PA2/Makefile`
+ Test the lexer on a source file. Outputs the tokenized lexemes:<br/>
`./lexer test.cl`

# Parser

# Semantic Analyzer
+ The semantic analyzer uses the abstract syntax tree (AST) from the parser to check for erroneous programs.
+ Looks at all classes and builds an inheritance graph
+ Checks if the graph is well-formed
+ In each class:
    + Gather all declarations in a symbol table traversing the AST
    + Check each expression for type correctness
    + Annotate the AST with types
    
+ Import all the tools needed for later compilation:<br/>
`make -f /usr/class/cs143/assignments/PA4/Makefile`
+ Build the semantic analyzer from the C++ code:<br/>
`make semant`
+ Test on a COOL file:<br/>
`./mysemant bad.cl`

# Code Generator

# Version of tools
flex: `2.5.4`  
bison: `3.5.1`  
g++: `9.4.0`  
spim: `6.5`  
os: `ubuntu 20.04`

# References
Needed flex-old to compile lexer:
https://stackoverflow.com/questions/34782625/undefined-reference-to-yylex

Compiler Tools from the Stanford Virtual Machine:
https://github.com/frevib/stanford-compilers-course-material

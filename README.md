# Compiler-COOL

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

# Version of tools
flex: `2.5.4`  
bison: `3.5.1`
g++: `9.4.0`  
os: `ubuntu 20.04`

# References
Needed flex-old to compile lexer:
https://stackoverflow.com/questions/34782625/undefined-reference-to-yylex

Compiler Tools from the Stanford Virtual Machine:
https://github.com/frevib/stanford-compilers-course-material

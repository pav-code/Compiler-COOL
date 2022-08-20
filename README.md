# Compiler-COOL

# Lexer
Needed flex-old to compile lexer:
https://stackoverflow.com/questions/34782625/undefined-reference-to-yylex

Compiler Tools from the Stanford Virtual Machine:
https://github.com/frevib/stanford-compilers-course-material

flex version 2.5.4

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


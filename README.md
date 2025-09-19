# Ex-3-RECOGNITION-OF-A-VALID-ARITHMETIC-EXPRESSION-THAT-USES-OPERATOR-AND-USING-YACC
# Date:19.9.2025
# AIM
To write a yacc program to recognize a valid arithmetic expression that uses operator +,- ,* and /.
# ALGORITHM
1.	Start the program.
2.	Write a program in the vi editor and save it with .l extension.
3.	In the lex program, write the translation rules for the operators =,+,-,*,/ and for the identifier.
4.	Write a program in the vi editor and save it with .y extension.
5.	Compile the lex program with lex compiler to produce output file as lex.yy.c. eg $ lex filename.l
6.	Compile the yacc program with yacc compiler to produce output file as y.tab.c. eg $ yacc –d arith_id.y
7.	Compile these with the C compiler as gcc lex.yy.c y.tab.c
8.	Enter an arithmetic expression as input and the tokens are identified as output.
# PROGRAM
```
%{
#include "y.tab.h"
%}

digit   [0-9]
%%
[ \t\n]+        ; // Ignore whitespace
{digit}+        { yylval = atoi(yytext); return NUMBER; }
[\+\-\*/]       { return *yytext; }
\(              { return '('; }
\)              { return ')'; }
.               { return 0; }
%%
int yywrap() { return 1; }
```
# OUTPUT

<img width="912" height="774" alt="Screenshot (164)" src="https://github.com/user-attachments/assets/7d22694d-70c2-47ca-8d0d-5fd30dd1886c" />


# RESULT
A YACC program to recognize a valid arithmetic expression that uses operator +,-,* and / is executed successfully and the output is verified.

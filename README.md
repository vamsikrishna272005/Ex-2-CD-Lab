# Ex-2-GENERATION OF LEXICAL TOKENS LEX FLEX TOOL

# Name:Vamsi Krishna G

# Reg No:212223220120

# Date: 20-09-2025

# AIM:
To write a lex program to implement lexical analyzer to recognize a few patterns.
# ALGORITHM

1.	Start the program.

2.	Lex program consists of three parts.

     a.	Declaration %%

     b.	Translation rules %%

     c.	Auxilary procedure.

3.	The declaration section includes declaration of variables, maintest, constants and regular definitions.
4.	Translation rule of lex program are statements of the form

    a.	P1 {action}

    b.	P2 {action}

    c.	…

    d.	…

    e.	Pn {action}

5.	Write a program in the vi editor and save it with .l extension.

6.	Compile the lex program with lex compiler to produce output file as lex.yy.c. eg $ lex filename.l $ cc lex.yy.c
7.	Compile that file with C compiler and verify the output.
# Program:
```
%{
#include <stdio.h>
#include <ctype.h>
%}

%%

"if"        { printf("Keyword: %s\n", yytext); }
"else"      { printf("Keyword: %s\n", yytext); }
"while"     { printf("Keyword: %s\n", yytext); }
"for"       { printf("Keyword: %s\n", yytext); }

[0-9]+      { printf("Number: %s\n", yytext); }
[a-zA-Z_][a-zA-Z0-9_]*   { printf("Identifier: %s\n", yytext); }

"=="|"="    { printf("Operator: %s\n", yytext); }
"+"|"-"|"*"|"/" { printf("Operator: %s\n", yytext); }

[ \t\n]     ;   // Ignore whitespace
.           { printf("Unknown: %s\n", yytext); }

%%

int main(int argc, char **argv) {
    yylex();
    return 0;
}

int yywrap() {
    return 1;
}


```
# OUTPUT

<img width="1479" height="765" alt="Screenshot 2025-09-20 153843" src="https://github.com/user-attachments/assets/176541e8-3d9f-4565-a4ed-667fa705e4e1" />


# RESULT
The lexical analyzer is implemented using lex and the output is verified.

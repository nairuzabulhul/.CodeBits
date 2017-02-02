
##### Jan 30 

#### Key Terms:

- Python parser 
- Shift parser
- Parsesd Tree
- Abstract Syntax Tree
- side effect ???
- impure vs pure languages
- Parser 
- lexing example :
- Tokens:
result = oldsum - value /100

__tokens__:
- IDENT : result, ASSIGN IDENT:oldsum SUB IDENT:value DIV NUMBER:100 EOS

__The above is an example of parsing__

- ASSIGN
- SUB
- DIV
- NUMBER
- EOS

__What is the difference between lexing and lexem?__

__Lexing__ takes the lex (word) of every unit and assign a token representation for it 

Ex: var x = 12 +8 
__output of lexer__
VAR IDENT:x ASSIGN NUMBER:12 ADD NUMBER:8

##### keyword
VAR : var __the variable is unchangeble with the vale of var__
FUNCTION:function
RETURN: return
PRITN: print 

__Program__
function SquareDistance(x1, y1, x2, y2){
    return x1 ^ x2 + y1  ^ y2 
}
var distance = SquareDistance(2,3,5,6)

FUNCTION IDENT:SquareDistance LPAREN IDENT:x1 COMMA IDENT:y1 COMMA IDENT:x2 COMMA IDENT:y2 RPAREN LBRACE RETURN IDENT:x1 EXP 
IDENT:x2 ADD IDENT:y1 EXP IDENT y2 RBRACE

VAR IDENT:distance ASSIGN IDENT:SquareDistance LPAREN NUMBER:2
COMMA NUMBER:3 COMMA NUMBER:5 COMMA NUMBER:6 RPAREN

##### This language is called Quirk, it has not Bolean language

Active lexing:is scanning 


__Feb,02,2017__

__[+ -]__ ? --> ? mean options, positive and negative numbers
__\d +__ --> for digits , one or more
__"*"__---> 0 or 1
__"\ \ "__ means that all characters, or numbers
__"\.\d*"__ means all numbers from 0 to any


####### Assignment :

- Lexer
- Parser
- Interpreter



# compilers24_compiler

---

# EBNF Very Complex Expression

```ebnf
prg              = prgHeader varDefs "begin" statementSeq "end" "."
prgHeader        = "program" identifier ";"
varDefs          = [ "var" varSeq { varSeq } ]
varSeq           = identifier { "," identifier } ":" type ";"
type             = "integer" | "string"

statementSeq     = { ( assignment | writeCall ) ";" }

assignment       = identifier ":=" expression
writeCall        = "write" "(" identifier ")" ";"

expression       = term { addOp term }
term             = factor { mulOp factor }
factor           = operand | "(" expression ")"
operand          = identifier | number | stringLiteral

addOp            = "+" | "-"
mulOp            = "*" | "/"

identifier       = letter { letter | digit }
number           = digit { digit }
stringLiteral    = '"' { printableChar } '"'
letter           = "a"..."z" | "A"..."Z"
digit            = "0"..."9"
printableChar    = any printable ASCII character except '"'
```

---

This Markdown formatting ensures that the EBNF is presented clearly and legibly within documentation or code repositories.

---

## EBNF With Functions

```ebnf
prg              = prgHeader varDefs { funcDef } "begin" statementSeq "end" "."
prgHeader        = "program" identifier ";"
varDefs          = [ "var" varSeq { varSeq } ]
varSeq           = identifier { "," identifier } ":" type ";"
type             = "integer" | "string"

funcDef          = "function" identifier "(" [paramSeq] ")" ":" type ";" varDefs "begin" statementSeq returnStmt "end" ";"
paramSeq         = identifier ":" type { "," identifier ":" type }
returnStmt       = "return" operand ";"

statementSeq     = { ( assignment | funcCall | writeCall ) ";" }

assignment       = identifier ":=" expression
funcCall         = identifier "(" [argumentSeq] ")"
argumentSeq      = operand { "," operand }
writeCall        = "write" "(" identifier ")" ";"

expression       = term { addOp term }
term             = factor { mulOp factor }
factor           = operand | "(" expression ")"
operand          = identifier | number | stringLiteral | funcCall

addOp            = "+" | "-"
mulOp            = "*" | "/"

identifier       = letter { letter | digit }
number           = digit { digit }
stringLiteral    = '"' { printableChar } '"'
letter           = "a"..."z" | "A"..."Z"
digit            = "0"..."9"
printableChar    = any printable ASCII character except '"'
```

---














# Roadmap

Future updates for planned releases will be maintained here as the project progresses.

## 0.0.1-beta

The following has been implemented (to one degree or another):

- allow *line numbers*
- support *labels*
- case-insensitive
- [LET](LET) is optional; however, variable types are currently *inferred* based on initial expression type (determined)
- `+ - * / \ ^ () = < > >= <= <>`
- Operator Precedence ([IMP](IMP), [EQV](EQV), [XOR](XOR), [OR](OR), [AND](AND), [NOT](NOT), `= > >= < <= <>`, `+ - binary`, [MOD](MOD), `\`, `* /`, `+ - unary`, `^`)

While the following still needs to be implemented:

- add support for arrays
- add support for numeric suffix types (beyond string `$`)
- add support for different numeric types; currently only supports INT32

The keywords below have been implemented if presented as a link to the documentation; otherwise, still needs to be handled.

### A

[ABS](ABS), ABSOLUTE, ACCESS, [AND](AND), ANY, APPEND, AS, [ASC](ASC), [ATN](ATN)

### B

[BASE](BASE), BEEP, BINARY, BLOAD, [Boolean Operators](boolean), BSAVE

### C

CALL, CALL ABSOLUTE, CASE, CDBL, CHAIN, [CHDIR](CHDIR), [CHR$](CHR$), CINT, CIRLCE, [CLEAR](CLEAR), CLNG, CLOSE, [CLS](CLS), [COLOR](COLOR), COM(n), COMMON, [CONST](CONST), [COS](COS), CSNG, CSRLIN, CVD, CVDMBF, CVI, CVL, CVS, CVSMBF

### D

DATA, DATE$, DECLARE, [DEF FN](DEF-FN), DEF SEG, DEFDBL, DEFINT, DEFLNG, DEFSNG, DEFSTR, [DIM](DIM), DO...LOOP, DO UNTIL, DO WHILE, DOUBLE, DRAW

### E

ELSE, ELSEIF, [END](END), END IF, ENVIRON, ENVIRON$, EOF, [EQV](EQV), ERASE, ERDEV, ERDEV$, ERL, ERR, ERROR, EXIT, [EXP](EXP)

### F

FIELD, FILEATTR, [FILES](FILES), FIX, [FOR...NEXT](FOR...NEXT), FRE, FREEFILE, [FUNCTION](FUNCTION)

### G

GET, GET#, [GOSUB](GOSUB), [GOTO](GOTO)

### H

[HEX$](HEX$)

### I

[IF...THEN](IF...THEN), [IMP](IMP), INKEY$, INP, [INPUT](INPUT), INPUT#, INPUT$, [INSTR](INSTR), [INT](INT), INTEGER, IOCTL, IOCTL$, IS

### K

KEY, KEY(n), [KILL](KILL)

### L

LBOUND, [LCASE$](LCASE$), [LEFT$](LEFT$), [LEN](LEN), [LET](LET), LINE, LINE INPUT, LINE INPUT#, LOC, LOCATE, LOCK, LOF, [LOG](LOG), LONG, LOOP, LPOS, LPRINT, LPRINT USING, LSET, LTRIM$

### M

[MID$](MID$), [MID$ (Statement)](MID$-Statement), MKD$, [MKDIR](MKDIR), MKDMBF$, MKI$, MKL$, MKS$, MKSMBF$, [MOD](MOD)

### N

[NAME](NAME), [NEXT](NEXT), [NOT](NOT)

### O

[OCT$](OCT$), OFF, ON, ON COM(n), ON ERROR GOTO, ON KEY(n), ON PEN, ON PLAY(n), ON STRIG(n), ON TIMER(n), ON...GOSUB, ON...GOTO, [OPEN], OPEN "COM(n), [OPTION BASE](OPTION-BASE), [OR](OR), OUT, OUTPUT

### P

[PRINT](PRINT)

PAINT, PALETTE, PALETTE USING, PCOPY, PEEK, PEN, PLAY, PLAY(n), PMAP, POINT, POKE, POS, PRESET, [PRINT](PRINT), PRINT USING, PRINT#, PRINT# USING, PSET, PUT, PUT#

### R

RANDOM, RANDOMIZE, READ, REDIM, [REM](REM), RESET, RESTORE, RESUME, [RETURN](RETURN), [RIGHT$](RIGHT$), [RMDIR](RMDIR), [RND](RND), RSET, RTRIM$, [RUN](RUN)

### S

SCREEN, SCREEN Function, SEEK, SEEK (Statement), SELECT, [SGN](SGN), SHARED, SHELL, [SIN](SIN), SINGLE, SLEEP, SOUND, [SPACE$](SPACE$), [SPC](SPC), [SQR](SQR), STATIC, [STEP](STEP), STICK, [STOP](STOP), [STR$](STR$), STRIG, STRIG(n), STRING, [STRING$](STRING$), SUB, SWAP, [SYSTEM](SYSTEM)

### T

[TAB](TAB), [TAN](TAN), [THEN](THEN), TIME$, TIMER, [TO](TO), TRON, TROFF, TYPE

### U

UBOUND, [UCASE$](UCASE$), UNLOCK, UNTIL, USING

### V

[VAL](VAL), VARPTR, VARPTR$, VARSEG, VIEW, VIEW PRINT

### W

WAIT, [WHILE...WEND](WHILE...WEND), WIDTH, WINDOW, WRITE

### X

[XOR](XOR)

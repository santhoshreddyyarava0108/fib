# fib
ORG 100h

MOV AH, 01h
INT 21h
SUB AL, '0'
MOV CL, AL

MOV AL, 0
MOV BL, 1

CMP CL, 0
JE DisplayResult
CMP CL, 1
JE DisplayResult

DEC CL

FibonacciLoop:
    ADD AL, BL
    XCHG AL, BL
    DEC CL
    JNZ FibonacciLoop

DisplayResult:
    ADD BL, '0'
    MOV DL, BL
    MOV AH, 02h
    INT 21h

MOV AH, 4Ch
INT 21h

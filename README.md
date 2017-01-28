# L8cpu

4 registers
256 bytes of memory

opcode reg X reg Y
0	0 0 0 0       xx  yy   	HLT
1	0 0 0 1       xx  yy	ADD - x = x + y
2	0 0 1 0       xx  yy	ADC - x = x + y + 1
3	0 0 1 1       xx  yy	SUB - x = x - y
	
4	0 1 0 0       xx  yy	SBC - x = x - y - 1
5	0 1 0 1       xx  yy	AND - x = x and y
6	0 1 1 0       xx  yy	OR  - x = x or y	
7	0 1 1 1       xx  yy	XOR - x = x xor y
	
8	1 0 0 0       xx  yy	NOT - x = !x

9	1 0 0 1       xx  00	INC - x = x + 1
                      xx  01	

A	1 0 1 0       xx  yy    CLF - clear flags?

B	1 0 1 1       xx  00    JMP - Jump to value in register a
	              xx  01    JMP - if not zero
                      xx  10    ?
		      xx  11    ?
	
C	1 1 0 0       xx  00    ?
D	1 1 0 1       xx  yy	?
	
E	1 1 1 0       xx  00    LD - load mem reg x
		      xx  01    LD - load immediate
                      xx  10    IN - input to reg x
		      xx  11    ?

F	1 1 1 1       xx  00    STR - store reg x to mem
                      xx  01    OUT - reg x to out  


t0 mar <= ip ? halt
t1 ir  <= mem , ip+1

t2 mar <= ip

t3 mbr <= mem , ip+1
t4 mar <= mbr 

t5 mbr <= reg | mbr <= mem
t6 reg <= mbr | mem <= mbr | ip <= mbr



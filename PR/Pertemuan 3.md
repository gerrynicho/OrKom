# Pekerjaan rumah: Buku Hamacher 2.5 & 2.9
### 2.5 [E] Write a RISC-style program that computes the expression SUM = 580 + 68400 + 80000.
```md
CLEAR R1
ADD R1, #580
ADD R1, #68400
ADD R1, #80000
STORE R1, SUM
```
### 2.9 [M] Rewrite the addition loop in Figure 2.8 so that the numbers in the list are accessed in the reverse order; that is, the first number accessed is the last one in the list, and the last number accessed is at memory location NUM1. Try to achieve the most efficient way to determine loop termination. Would your loop execute faster than the loop in Figure 2.8?
```md
	    LOAD			    R2, N
	    CLEAR 			    R3
	    MOVE 			    R4, #NUM1
LOOP1: 	ADD			        R4, #4
	    SUBTRACT		    R2, #1
	    BRANCH_IF_[R2]>1 	LOOP1
LOOP2:	ADD			        R3, (R4)
	    SUBTRACT		    R4, #4
	    ADD			        R2, #1
	    Branch_If_[R2]<=N	LOOP2
	    STORE			    R3, SUM

```
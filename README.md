# LL1-Parser
LL1 parser implementation. A program to generate an LL(1) parser for a given grammar and to parse input strings.

## Input
```
S
S->aSb
S->A
A->c
aacbb
```
## Output
```console
Enter file name :- 
grammar.txt
Start Variable :- S
Variables :-  A S 
Terminals :-  a b c 
Production Rules :-
A -> c
S -> aSb | A

First:-
A -> { c }
S -> { a , c }

Follow:-
A -> { $ , b }
S -> { $ , b }

Table :-
Variable :- A Terminal :- c Rule :- c
Variable :- S Terminal :- a Rule :- aSb
Variable :- S Terminal :- c Rule :- A


Parsing Start.......

	STACK			INPUT			ACTION
	$S		        aacbb$			Shift ,S->aSb
	$bSa			aacbb$			Reduce
	$bS			acbb$			Shift ,S->aSb
	$bbSa			acbb$			Reduce
	$bbS			cbb$			Shift ,S->A
	$bbA			cbb$			Shift ,A->c
	$bbc			cbb$			Reduce
	$bb		    	bb$			Reduce
	$b		    	b$			Reduce
	$		    	$			Done

Result :- Accepted

```


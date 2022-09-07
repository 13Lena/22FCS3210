# Formal Grammars

For each of the grammars from Q1-3, classify them as either regular or context-free. Then answer yes/no whether each word can be generated from the grammar. If you answer yes, show the sequence of productions to generate the word.  When you are done, submit this README.md file with your answers on Canvas. 

## Q1 ~context free

```
G = (V, T, P, S) 
V = {S, NP, NOM, VP, Det, Noun, Verb, Aux}
T = {that, this, a, the, man, book, flight, meal, include, read, does}
P = {
    S → NP VP 
    S → Aux NP VP 
    S → VP 
    NP → Det NOM 
    NOM → Noun
    NOM → Noun NOM
    VP → Verb
    VP → Verb NP
    Det → that | this | a | the
    Noun → book | flight | meal | man
    Verb → book | include | read
    Aux → does
} 
```
 
### a) ~yes

```
does a meal include a book 

S ->
Aux NP VP ->
does NP VP ->
does Det NOM VP ->
does a NOM VP ->
does a meal VP ->
does a meal Verb NP ->
does a meal include NP ->
does a meal include Det NOM ->
does a meal include a NOM ->
does a meal include a Noun ->
does a meal include a book
```

### b) ~yes

```
this flight book a meal

S ->
NP VP ->
Det NOM VP ->
this NOM VP ->
this flight VP ->
this flight Verb NP ->
this flight book NP ->
this flight book Det NOM ->
this flight book a NOM ->
this flight book a meal
``` 

### c) ~yes

```
a man read a book

S ->
NP VP ->
Det NOM VP ->
a NOM VP ->
a Noun VP ->
a man VP ->
a man Verb NP ->
a man read NP ->
a man read Det NOM ->
a man read a NOM ->
a man read a Noun ->
a man read a book
```

## Q2 ~context free
```
G = ({S, A, B}, {a, b}, P, S) 
P = {S → aA, A → bB | ε, B → aA}    
```

### a) ~yes

```
a

S ->
aA ->
aε ->
a
```

### b) ~yes

```
aba

S ->
aA ->
abB ->
abaA ->
abaε ->
aba
```

### c) ~no, cannot get two "b" next to eachother

```
bb
```

### d) ~no, cannot get two "b" next to eachother

```
abb
```

## Q3 ~context free

```
G = ({S, A}, {0, 1}, P, S) 
P = {S → A0, A→A01|ε}           
```
 
### a) ~no, cannot have two "0" together

```
00
```
 
### b) ~ no, cannot generate a "ε" without getting a "0" 

```
ε
```

### c) ~ yes

```
010

S ->
A0 ->
A010 ->
ε010 ->
010
```
 
### d) ~ yes

```
0101010

S ->
A0 ->
A010 ->
A01010 ->
A0101010 ->
ε0101010 ->
0101010
``` 

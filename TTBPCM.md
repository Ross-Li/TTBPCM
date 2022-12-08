# TTBPCM: Tips Tricks Best Practices Common Mistakes

---
# Tips Tricks Best Practices

## 1. Use pen and paper when you don't know how to code this stuff (2022.12.05)
Use pen and paper to draw data structures and how the "frameshots" of program execution. Helps tremendously with thinking clearly.
e.g. 

## 2. After writing a loop, write the modification of loop variable to ensure it will exit IMMEDIATELY. (2022.12.06)
Similarly, after allocating memory, IMMEDIATELY think about where and how to free it.
e.g. After writing:

```cpp
while (count < iteration) {
   
}
```
IMMEDIATELY write:

```cpp
while (count < iteration) {
   count++;
}
```

## 3. Inversion technique to "denest" (2022.12.08)
Source: [Why You Shouldn't Nest Your Code - CodeAesthetic](https://www.youtube.com/watch?v=CFRhGnuXG-4&list=WL&index=2)
Never make your code over 3 indentions deep.
It is better to refactor this:
```cpp
if (condition) {
   // a LONG piece of code
} else {
   // a SHORT piece of code, that can be easliy done or can be done first 
   // e.g. check for error, throwing exceptions 
}
```

to this:
```cpp
if (!condition) {
   // a SHORT piece of code, that can be easliy done or can be done first 
   // e.g. check for error, throwing exceptions 
}

// a LONG piece of code
```
## 4. Always check and tackle the special cases FIRST
Special cases may include:
+ What if there is no input?
+ What if the input is illegal and you need to throw exceptions?


---
# Common Mistakes & Ways to Detact and Fix Them

## 1. If the program outputs 0 or gibberish, it is very likely that you have a memory problem. (2022.12.02)
+ You didn't declare something properly and the compiler did it for you.
+ You declared something but didn't initialize it.
e.g. The CSC4005 MPI problem. Something is declared in all processes, BUT only initialized in master process.


---
# Temp Area

![](https://s2.loli.net/2022/11/26/PG8gseQ5qSay73B.png)

While multi-process programming, considering adding buffer to each process for sending, receving and temporarily storing and updating something.

![Imgur](https://i.imgur.com/YZwJ4ZR.png)

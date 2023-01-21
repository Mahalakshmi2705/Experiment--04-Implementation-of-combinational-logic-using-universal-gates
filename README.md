Experiment--04-Implementation-of-combinational-logic-using-universal-gates

Implementation of combinational logic using universal-gates

 
AIM:
   
   To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate

Equipments Required:

  Hardware – PCs, Cyclone II , USB flasher
  
  Software – Quartus prime


Theory:

Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

Using NAND gates

NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'


Using NOR gates

NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'


Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.

Developed by : MAHALAKSHMI S 

RegisterNumber:  22008601

procedure

PROGRAM 1:

module expfourone(a,b,c,d,f);

input a,b,c,d;

output f;

wire f1,f2,f3;

assign f1 = (~c&~b&~a);

assign f2 = (~d&~c&~a);

assign f3 = (c&~(~b)&~a);

assign f= f1&~f2&~f3;

endmodule

PROGRAM 2:

module expfourtwo(a,b,c,d,f);

input a,b,c,d;

output f;

wire f1,f2,f3,f4;

assign f1 = c&(~b)&a;

assign f2 = d&(~c)&a;

assign f3 = c&(~b)&a;

assign f4 = ~(f1|f2|f3);

not(f,f4);

endmodule

OUTPUT:

RTL realization:

FOR PROGRAM 1:

![Screenshot (70)](https://user-images.githubusercontent.com/122199968/213875096-e55c6d6d-be84-46ea-be54-3137e7f91e3b.png)


FOR PROGRAM 2:

![Screenshot (71)](https://user-images.githubusercontent.com/122199968/213875158-44e199e0-adcf-4f46-95d0-39928992e62b.png)


TRUTH TABLE:

FOR PROGRAM 1:

![Screenshot (72)](https://user-images.githubusercontent.com/122199968/213875221-7523a059-14fb-48bf-a02e-a0e60a211a56.png)

FOR PROGRAM 2:

![Screenshot (73)](https://user-images.githubusercontent.com/122199968/213875280-81b993fe-fcfc-4c8a-8057-e06e0db4b340.png)

TIMING DIAGRAM:

FOR PROGRAM 1:


![Screenshot (74)](https://user-images.githubusercontent.com/122199968/213875325-10ec35b9-9495-4153-b5ef-b62839f78f22.png)


FOR PROGRAM 2:


![Screenshot (75)](https://user-images.githubusercontent.com/122199968/213875394-cd835930-8d9b-4b2c-970b-84b65e8f972c.png)

RESULT:

Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.





## Output:
## RTL
## Timing Diagram
## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.

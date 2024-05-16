EXP-1

date:

                 SIMULATION OF LOGIC GATES ,ADDERS AND SUBTRACTORS

AIM: To simulate Logic Gates ,Adders and Subtractors using Vivado 2023.2.

APPARATUS REQUIRED: VIVADO 2023.2

PROCEDURE:

STEP:1 Launch the Vivado 2023.2 software.

STEP:2 Click on “create project ” from the starting page of vivado.

STEP:3 Choose the design entry method:RTL(verilog/VHDL).

STEP:4 Crete design source and give name to it and click finish.

STEP:5 Write the verilog code and check the syntax.

STEP:6 Click “run simulation” in the navigator window and click “Run behavioral simulation”.

STEP:7 Verify the output in the simulation window.

LOGIC GATES LOGIC DIAGRAM:

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-1/assets/161431337/53b77317-f20c-4938-b59d-8fb6d4e44d21)

VERILOG CODE:
```
module logicgate (a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);
input a,b;  
output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;
and(andgate,a,b);
or(orgate,a,b);
xor(xorgate,a,b);
nand(nandgate,a,b); 
nor(norgate,a,b);
xnor(xnorgate,a,b);
not(notgate,a);
endmodule
```

OUTPUT WAVEFORM :

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-1/assets/161431337/0ed84e75-720c-476d-9b30-a06b0990312f)

HALF ADDER LOGIC DIAGRAM :

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-1/assets/161431337/54a3ed51-c4a1-4b3a-a369-383bf9d4f0b9)

VERILOG CODE:
```
module half_adder(a,b,sum,carry);

input a,b;

output sum,carry;

xor g1(sum,a,b);

and g2(carry,a,b);

endmodule
```

OUTPUT WAVEFORM:

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-1/assets/161431337/42c9456d-0e2a-4bdd-8d86-35c3a33d9797)

FULL ADDER LOIC DIAGRAM :

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-1/assets/161431337/daeab419-fa43-4819-ab76-dd0a48bbe91f)

VERILOG CODE :
```
module fulladder(a,b,c,sum,carry);

input a,b,c;

output sum,carry;

wire w1,w2,w3;

xor(w1,a,b);

xor(sum,w1,c);

and(w2,w1,c);

and(w3,a,b);

or(carry,w2,w3);

endmodule
```

OUTPUT WAVEFORM:

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-1/assets/161431337/165171c9-e1f7-43da-a6b3-3bdcfe9d188c)

HALF SUBRACTOR LOGIC DIAGRAM:

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-1/assets/161431337/181ebd8f-1d9a-4a2a-ae39-36c89a9329a5)

VERILOG CODE:
```
module halfsub(a,b,diff,borrow);

input a,b;

output diff,borrow;

xor(diff,a,b);

and(borrow,~a,b);

endmodule
```

OUTPUT WAVEFORM:

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-1/assets/161431337/68c1d378-aa8d-41a2-92d6-0dcbbb3ebbbc)

FULL SUBRACTOR LOGIC DIAGRAM:

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-1/assets/161431337/29eb184c-68eb-4cde-a8bb-5f341d52e0a7)

VERILOG CODE:
```
module fs(a,b,bin,d,bout);

input a,b,bin;

output d,bout;

wire w1,w2,w3;

xor(w1,a,b);

xor(d,w1,bin);

and(w2,~a,b);

and(w3,~w1,bin);

or(bout,w3,w2);

endmodule
```

OUTPUT WAVEFORM:

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-1/assets/161431337/0c690339-9238-4494-8fdf-1bb55bdcec21)

RIPPLE CARRY ADDER LOGIC DIAGRAM:

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-1/assets/161431337/6cc61c50-3265-48f8-b3f6-c85903be2bd4)

VERILOG CODE:
```
module fulladder(a,b,c,sum,carry);
input a,b,c;
output sum,carry;
wire w1,w2,w3;
xor(w1,a,b);
xor(sum,w1,c);
and(w2,w1,c);
and(w3,a,b);
or(carry,w2,w3);
endmodule

module rca_8bit(a,b,cin,s,cout);
input [7:0]a,b;
input cin;
output [7:0]s;
output cout;
wire [7:1]w;
fulladder f1(a[0], b[0], cin, s[0], w[1]);
fulladder f2(a[1], b[1], w[1], s[1], w[2]);
fulladder f3(a[2], b[2], w[2], s[2], w[3]);
fulladder f4(a[3], b[3], w[3], s[3], w[4]);
fulladder f5(a[4], b[4], w[4], s[4], w[5]);
fulladder f6(a[5], b[5], w[5], s[5], w[6]);
fulladder f7(a[6], b[6], w[6], s[6], w[7]);
fulladder f8(a[7], b[7], w[7], s[7], cout);
endmodule
```

OUTPUT WAVEFORM:

![image](https://github.com/Tarunkola1/VLSI-LAB-EXP-1/assets/161431337/be25ce68-e27d-4a28-97d9-e62bfc978e74)

RESULT:

SIMULATION OF LOGIC GATES,ADDERS AND SUBRACTORS USING VIVADO 2023.2 IS VERIFIED.

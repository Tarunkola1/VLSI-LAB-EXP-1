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

LOGIC GATES LOGIC DIAGRAM :

![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161431337/91ba7a79-0178-4ca6-9e12-0a0ff50b35fd)

VERILOG CODE
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

OUTPUT WAVEFORM
![328455264-a62e4538-0094-4126-b762-1a1fdc1e8931](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161431337/35cd502f-3c0a-445c-8e02-6cc45d271711)

HALF ADDER LOGIC DIAGRAM

![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161431337/44a3934e-b7d9-47b9-8a3e-2a4cdf9b201f)

VERILOG CODE :
```
module half_adder(a,b,sum,carry);

input a,b;

output sum,carry;

xor g1(sum,a,b);

and g2(carry,a,b);

endmodule
```

OUTPUT WAVEFORM:

![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161431337/8e8056c2-cae2-4c84-90ed-306d911c66d0)

FULL ADDER LOGIC DIAGRAM:

![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161431337/91d0bd80-170c-44c5-af56-69bf6ebac7bb)

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
```

OUTPUT WAVEFORM:

![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161431337/0c060f32-886e-46cb-9cc6-822eaa324087)

FULL ADDER LOGIC DIAGRAM:

![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161431337/04ad8dce-3aa9-4fea-ae3d-e6ba9aff9d3f)

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

![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161431337/46fe99d1-6ea4-423d-bfcc-2bb21956551a)

RIPPLE CARRY ADDER LOGIC DIAGRAM:

![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161431337/b045b002-8159-4585-af34-7a11472f001b)

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

![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/161431337/cdbc2b32-ca9e-4bab-849a-1d5f15b87577)

RESULT:
   simulation of Logic Gates ,Adders and Subtractors using Vivado 2023.2 is verified.














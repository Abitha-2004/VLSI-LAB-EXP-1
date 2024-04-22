# VLSI-LAB-EXPERIMENTS
AIM: To simulate and synthesis fulladder,fullsubractor,halfadder,halfsubractor,logicgates,ripplecarryadder_8 using vivado 2023.1

APPARATUS REQUIRED: vivado 2023.1

PROCEDURE:1. Open Vivado: Launch Xilinx Vivado software on your computer.

2. Create a New Project: Click on "Create Project" from the welcome page or navigate through "File" > "Project" > "New".

3. Project Settings: Follow the prompts to set up your project. Specify the project name, location, and select RTL project type.

4. Add Design Files: Add your Verilog design files to the project. You can do this by right-clicking on "Design Sources" in the Sources window, then selecting "Add Sources". Choose your Verilog files from the file browser.

5. Specify Simulation Settings: Go to "Simulation" > "Simulation Settings". Choose your simulation language (Verilog in this case) and simulation tool (Vivado Simulator).

6. Run Simulation: Go to "Flow" > "Run Simulation" > "Run Behavioral Simulation". This will launch the Vivado Simulator and compile your design for simulation.

7. Set Simulation Time: In the Vivado Simulator window, set the simulation time if it's not set automatically. This determines how long the simulation will run.

8. Run Simulation: Start the simulation by clicking on the "Run" button in the simulation window.

9. View Results: After the simulation completes, you can view waveforms, debug signals, and analyze the behavior of your design.


Logic Diagram :

Logic Gates:
![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)


Half Adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)


Full adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)


Half Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)



Full Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)



8 Bit Ripple Carry Adder

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)



VERILOG CODE:
LOGICGATES:
~~~
module logicgates(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);
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
~~~
OUTPUT:
![image](https://github.com/Abitha-2004/VLSI-LAB-EXP-1/assets/161303006/e5640060-581d-470e-91a6-cbaa2a76ff40)
![image](https://github.com/Abitha-2004/VLSI-LAB-EXP-1/assets/161303006/eaf20fdd-7985-446f-a367-7caaf4278afa)
HALFADDER:
~~~
module half_adder(a,b,sum,carry);
input a,b;
output sum,carry; // sum and carry
assign sum = a^b;
assign carry = a&b ;
endmodule
~~~
OUTPUT:
![image](https://github.com/Abitha-2004/VLSI-LAB-EXP-1/assets/161303006/b8319261-7069-4bae-88fc-c89764e4413d)
![image](https://github.com/Abitha-2004/VLSI-LAB-EXP-1/assets/161303006/ecba6e70-a3a8-4a4a-aff0-9b9dd9f42a1d)
FULLADDER:
~~~
module full_adder(sum,count,a,b,c);
input a,b,c;
output sum,cout;
  wire w1,w2,w3,w4,w5;
  xor x1(w1,a,b);
  xor x2(sum,w1,c);  
  and a1(w2,a,b);
  and a2(w3,b,c);
  and a3(w4,a,c);
  
  or o1(w5,w2,w3);
  or o2(cout,w5,w4);
    
endmodule
~~~
OUTPUT:
![image](https://github.com/Abitha-2004/VLSI-LAB-EXP-1/assets/161303006/825a4214-975f-463d-be68-7a97e9af2d8a)
![image](https://github.com/Abitha-2004/VLSI-LAB-EXP-1/assets/161303006/9134cd2e-dce8-43d9-b0c2-d681f75c4a08)
HALFSUBTRACTOR:
~~~
module halfsubtractor( D,Bo,A,B);
input A,B;
output D,Bo;
wire w1;
xor (D,A,B);
not (w1,B);
and (Bo,B,w1);
endmodule
~~~
OUTPUT:
![image](https://github.com/Abitha-2004/VLSI-LAB-EXP-1/assets/161303006/a66cb942-5711-43cf-b8f8-edc21bd7b202)
![image](https://github.com/Abitha-2004/VLSI-LAB-EXP-1/assets/161303006/92ada442-945d-4e7e-ba30-1f30e3885ca8)
FULLSUBRACTOR:
~~~
module full_sub(borrow,diff,a,b,c);
output borrow,diff;
input a,b,c;
wire w1,w4,w5,w6;
xor (diff,a,b,c);
not n1(w1,a);
and a1(w4,w1,b);
and a2(w5,w1,c);
and a3(w6,b,c);
or o1(borrow,w4,w5,w6);
endmodule
~~~
OUTPUT:
![image](https://github.com/Abitha-2004/VLSI-LAB-EXP-1/assets/161303006/08a081c2-107f-443c-892e-dc45dcce518f)
![image](https://github.com/Abitha-2004/VLSI-LAB-EXP-1/assets/161303006/0dad9190-a61f-474a-b5ab-911fc48da045)
8 Bit Ripple Carry Adder:
~~~


















RESULT:


# NAME=M Himavath
## REGISTER NUMBER=23010121
# Experiment-4 Half Subtractor and Full subtractor


## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:

Hardware – PCs, Cyclone II , USB flasher<br>
Software – Quartus prime

## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure
1)Create a New Project:

    *Open Quartus and create a new project by selecting "File" > "New Project Wizard."<br>
    *Follow the wizard's instructions to set up your project, including specifying the project name, location, and target device (FPGA).<br>
    
2)Create a New Design File:

    *Once the project is created, right-click on the project name in the Project Navigator and select "Add New File."<br>
    *Choose "Verilog HDL File" or "VHDL File," depending on your chosen hardware description language.
    
3)Write the Combinational Logic Code:

    *Open the newly created Verilog or VHDL file and write the code for your combinational logic.<br>
    
 4)Compile the Project:

    *To compile the project, click on "Processing" > "Start Compilation" in the menu.<br>
    *Quartus will analyze your code, synthesize it into a netlist, and perform optimizations based on your target FPGA device.<br>

5)Analyze and Fix Errors:

    *If there are any errors or warnings during the compilation process, Quartus will display them in the Messages window.<br>
    *Review and fix any issues in your code if necessary.<br>
    *View the RTL diagram.<br>
    
 6)Verification:

    *Click on "File" > "New" > "Verification/Debugging Files" > "University Program VWF".<br>
    *Once Waveform is created Right Click on the Input/Output Panel > " Insert Node or Bus" > Click on Node Finder > Click On "List" > Select All.<br>
    *Give the Input Combinations according to the Truth Table and then simulate the Output Waveform.<br>


## Program:
## Half Subtractor
```
module halfsub(diff,carry,a,b);
input a,b;
output diff,carry;
xor(diff,a,b);
assign carry=(~a)&b;
endmodule
```
## Full subtractor
```
module fullsub(diff,carry,a,b,c);
input a,b,c;
output diff,carry;
xor(diff,a,b,c);
assign carry= (~a)&c | (~a)&b | (b&c);
endmodule
```
## Truthtable
## Half Subtractor
![image](https://github.com/Himavath08/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/139110631/b070927a-d394-4c6b-a9df-2f0748e24962)

## Full subtractor
  ![image](https://github.com/Himavath08/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/139110631/6fe9e94c-0c19-4df1-9433-ef661d713a71)

##  RTL realization
## Half Subtractor
![image](https://github.com/Himavath08/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/139110631/1f8b81b2-2e75-4b79-8961-c86fc9b4de11)

## Full subtractor
![image](https://github.com/Himavath08/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/139110631/d8e5ea6e-2109-4a13-9441-0d89be31c160)

## Timing diagram 
## Half Subtractor
![image](https://github.com/Himavath08/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/139110631/fa9b3f60-d9af-4b3e-9710-8ca5c5e357d3)

## Full subtractor
![image](https://github.com/Himavath08/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/139110631/2bb49971-3ebc-4dc5-991d-dfeb25655db5)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.

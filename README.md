# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

Four-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
### Procedure
```
1.Create a new project in QuartusII software.
2.Name the project as uc for upcounter and dc for down counter.
3.Create a new verilog hdl file in the project file.
4.Name the module as dc and uc for down counter and up counter.
5.Within the module declare input and output variables.
6.Create a loop using if-else with condition parameter as reset value.
7.End the loop.
8.End the module.
```


### PROGRAM 
```
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by:yuva krishna k 
RegisterNumber:  212222110056

UP COUNTER:

module Counters(clk,A);
input clk;
output reg [3:0]A;
always @(posedge clk)
begin
	A[3]=(((A[0])&(A[1])&(A[2]))^A[3]);
	A[2]=(((A[0])&(A[1]))^A[2]);
	A[1]=(A[0])^A[1];
	A[0]=A[0]^1;
end
endmodule

DOWN COUNTER:

module dCounters(clk,A);
input clk;
output reg [3:0]A;
always@(posedge clk)
begin
	A[3]=(((~A[0])&(~A[1])&(~A[2]))^A[3]);
	A[2]=(((~A[0])&(~A[1]))^A[2]);
	A[1]=(~A[0])^A[1];
	A[0]=1^A[0];
end
endmodule

```





### RTL LOGIC UP COUNTER AND DOWN COUNTER  
## UP COUNTER:
![279409689-21a764f7-7623-4773-9c1a-5596fa793a0c](https://github.com/Yuvakrishna0/Exp-7-Synchornous-counters-/assets/117915037/88302ee7-5a96-4c50-a1df-8db74c572be7)


## DOWN COUNTER:


![279407474-c50e6119-92fa-4325-8d4f-48bda2c535c5](https://github.com/Yuvakrishna0/Exp-7-Synchornous-counters-/assets/117915037/291a790f-a82e-4c1c-a429-cf2269668994)




### TIMING DIGRAMS FOR COUNTER  

## UP COUNTER:
![279425738-32c085a6-28b6-471b-a0f6-f4eaf69998ee](https://github.com/Yuvakrishna0/Exp-7-Synchornous-counters-/assets/117915037/99c5b7d4-9d43-4c3a-8512-70dece8f03e9)


## DOWN COUNTER:

![277364858-48cdd927-573f-4ec9-8424-c99726ac4906](https://github.com/Yuvakrishna0/Exp-7-Synchornous-counters-/assets/117915037/66c56022-0a1a-4345-8fe9-91a5c518ceef)



### TRUTH TABLE 

## UP COUNTER:
![277365032-1ba2a248-1433-48ef-8a5b-bc0b25b540cb](https://github.com/Yuvakrishna0/Exp-7-Synchornous-counters-/assets/117915037/2e89b470-4c45-4174-afeb-965bd00bc6ed)


## DOWN COUNTER:
![277365146-5ce4df65-9958-42e0-9e69-22d099eec3ff](https://github.com/Yuvakrishna0/Exp-7-Synchornous-counters-/assets/117915037/6ca8594a-619f-45b2-8b7b-753244e38b6c)


### RESULTS :
Thus Synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.

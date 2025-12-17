### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

```
1.Open Quartus software and create a new Verilog file. Paste the code and save it.
2.Compile the program to check for errors.
3.Generate the RTL schematic via the RTL Viewer and save the logic diagram.
4.Use the Waveform Editor to assign nodes for clk, rstn, and out.
5.Simulate the design with different clk and rstn combinations to generate the timing diagram, and save the results.
```

**PROGRAM**
```
module upcounter(clk,rst,count);
input clk,rst;
output reg[3:0]count;
always@(posedge clk or negedge rst)
begin
if(!rst)
count <= 4'b0000;
else
count <= count+1;
end
endmodule

```

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by:NITESH BHANDARI K
RegisterNumber:25009039
*/

**RTL LOGIC UP COUNTER**

<img width="1919" height="969" alt="11expupcounter" src="https://github.com/user-attachments/assets/10c739e1-dbc3-4ef0-8848-02839c28faa4" />


**TIMING DIAGRAM FOR IP COUNTER**

<img width="1919" height="961" alt="11expupcounterwave" src="https://github.com/user-attachments/assets/6de42d7b-6eab-48c5-802c-e676fa08c7a9" />

**TRUTH TABLE**

![SYNCTRUTHTABLE](https://github.com/user-attachments/assets/dbe9c2fa-d735-4473-9ae5-b361b5e5ef1f)


**RESULTS**


Thus the Synchronous 4 bit Up counter is implemeted and verified.

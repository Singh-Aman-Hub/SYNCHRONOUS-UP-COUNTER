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

/*
1.Understand the Inputs and Outputs:
Inputs: clk (clock) and rst (reset).
Output: out is a 4-bit register that holds the counter value.
Define Counter Logic:

2.On each rising edge of the clock (posedge clk), check if rst (reset) is active.
If rst is high, reset out to 0.
Otherwise, increment out by 1.
Write and Save the Verilog Code:

3.Create a new Verilog file.
Write the code provided above to implement the counter.
Simulate the Design:

4.Create a testbench to provide the clk and rst signals.
Observe the counter behavior during simulation to ensure it increments and resets correctly.
Verify the Functionality:

5.Confirm that the counter increments from 0 to 15 and resets to 0 when rst is activated. */

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 
module ex11(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(rst)
     out<=0;
   else 
     out <= out+1;
end
endmodule


Developed by:AMAN SINGH
RegisterNumber: 24900215
*/

**RTL LOGIC UP COUNTER**
![Screenshot (1757)](https://github.com/user-attachments/assets/c3a75415-16fd-4e31-a1ef-4dd412b2ca73)


**TIMING DIAGRAM FOR IP COUNTER**
![Screenshot (1758)](https://github.com/user-attachments/assets/03344b4a-5921-4060-9504-302c23611d8b)


**TRUTH TABLE**
![image](https://github.com/user-attachments/assets/49415d55-b577-4d09-ba3a-7985edd2f8c7)



**RESULTS**

Thus 4 bit synchronous up counter was implemented successfully and its functionality validated.

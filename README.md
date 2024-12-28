# 4-BIT-RIPPLE-COUNTER

**AIM:**

To implement  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/cb4b74d4-31ab-4359-95d0-d22e67daba13)

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/a573a7d6-014e-4e54-93e6-e2ac9530960b)

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/85e1958a-2fc1-49bb-9a9f-d58ccbf3663c)

**Procedure**

/* write all the steps invloved */

1.Increment count on each positive edge of the clock.

2.Reset count to zero when it reaches 15.

3.Generate clock signal (clk).

4.Instantiate the RippleCounter module.

5.Conduct functional testing by displaying the count at each clock cycle for 16 cycles.

**PROGRAM**

/* Program for 4 Bit Ripple Counter and verify its truth table in quartus using Verilog programming.
```
//Module
module RippleCounter( input wire clk, output reg [3:0] count = 4'b0000 );
always @(posedge clk) begin if (count == 4'b1111) count <= 4'b0000; else count <=
count + 1; end
endmodule
// Testbench
module RippleCounter_tb;
reg clk; wire [3:0] count;
RippleCounter uut( .clk(clk), .count(count) );
initial begin clk = 0; forever #5 clk = ~clk; end
initial begin #10; $display("Time | Count"); $display("-----------------"); repeat (16) begin
#5; $display("%4d | %b", $time, count); end $finish; end
endmodule
```
 Developed by: RegisterNumber:
*/24000942

**RTL LOGIC FOR 4 Bit Ripple Counter**
![398903493-f411c490-aad5-4883-be11-3f718c08ee29](https://github.com/user-attachments/assets/a3c29458-0ea7-4b86-a0a0-4f7aa6ba15be)

**TIMING DIGRAMS FOR 4 Bit Ripple Counter**
![398903669-d4954d25-ab99-44ea-a341-519f37d753f1](https://github.com/user-attachments/assets/6597258f-d9fd-4315-99f8-60b7efcd4b67)

**RESULTS**
Thus the 4 Bit Ripple Counterhas been implemented using verilog andtheir functionality has been validated using their functional tables.

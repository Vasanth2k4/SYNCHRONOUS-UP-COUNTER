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

/* write all the steps invloved */

**PROGRAM**

```
module EXP11 (
    input clk,
    input rst,
    output reg [3:0] out
);

always @(posedge clk) begin
    if (rst)
        out <= 4'b0000;  // Reset to 0
    else
        out <= out + 1;  // Increment on each clock cycle
end

endmodule
module EXP12 (
    input clk,
    input rst,
    output reg [3:0] out
);

always @(posedge clk) begin
    if (rst)
        out <= 4'b1111;  // Reset to 15
    else
        out <= out - 1;  // Decrement on each clock cycle
end

endmodule
```

Developed by:Ramya G /  RegisterNumber: 212224220078
*/

**RTL LOGIC UP COUNTER**

![Screenshot 2025-05-07 141251](https://github.com/user-attachments/assets/2dbb921f-f462-42c2-8775-664f00b511c2)


**TIMING DIAGRAM FOR IP COUNTER**

![Screenshot 2025-05-07 141235](https://github.com/user-attachments/assets/be9030f3-28f7-41c7-9efc-8373807c20a1)


**TRUTH TABLE**

![image](https://github.com/user-attachments/assets/db2cf676-a2ab-454b-9876-79fe9132f011)


**RESULTS**

Thus the above program logigates is successfully excured and verified in QUTRUS II by using verilog HDL

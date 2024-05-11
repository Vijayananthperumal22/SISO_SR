# SISO_SR
# The shift register, which allows serial input (one bit after the other through a single data line) and produces a serial output is known as a Serial-In Serial-Out shift register. Since there is only one output, the data leaves the shift register one bit at a time in a serial pattern, thus the name Serial-In Serial-Out Shift Register. The logic circuit given below shows a serial-in serial-out shift register. The circuit consists of four D flip-flops which are connected in a serial manner. All these flip-flops are synchronous with each other since the same clock signal is applied to each flip-flop. 
![image](https://github.com/RESMIRNAIR/SISO_SR/assets/154305926/778bf654-f276-4c56-ab9b-33de0e21eac9)
# PROGRAM
```
module siso_shift_register( input wire clk, // Clock input input wire reset, // Reset input input wire serial_in, // Serial input output reg serial_out // Serial output );

// Initialize shift register reg [7:0] shift_reg = 8'b00000000;

always @(posedge clk or posedge reset) begin if (reset) begin // Reset shift register shift_reg <= 8'b00000000; serial_out <= 1'b0; end else begin // Shift data in shift_reg <= {shift_reg[6:0], serial_in}; // Shift in serial data

// Serial output
serial_out <= shift_reg[7];
end end

endmodule
```
# OUTPUT
![Uploading image.png…]()

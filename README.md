# Simple Processor

Final Lab Project for University of California, Riverside EE/CS120A Logic Design Course. 

## Contributors
**Matthew Lumantas:** In charge of designing Register Display and Control Unit components. Implemented theory of the Processor in a higher level state machine. Github: https://github.com/mattlumantas 


**Baldomero Vargas:** In charge of designing 10 Input Mux, Register Bank, ALU components.

## Project Description
This project consists of the implementation of the von Neumann model at the logic gate level using the Spartan3E FPGA based BASYS2 prototyping board. The machine is capable of moving 8-bit values between its eight registers, loading immediate values to a register, and adding or subtracting the values of two registers together. The control unit was designed using a finite state machine (FSM) model. Using FSM conversion techniques, we created a large truth table to coordinate the manipulation of data. The arithmatic logic unit is a simple adder with an added conversion step for use in subtraction. Input is handled using the BASYS2's onboard switches and buttons and output are seven segment displays with the contents of a selected register.

The memory unit must particularly be noted, as the entirety of the designed memory is eight 8-bit registers. Because we did not include larger-scale memory storage into the design, we did not implement a stored-program capability for the machine. Each instruction is encoded and executed individually. To add in this capability would require a thorough redesign of the control unit. This is due to two primary factors: the number of inputs available, and the FSM that the control logic is converted from. The BASYS2 board has eight switches and four buttons of input without any additional modules installed. We currently use all of these for our control: the eight switches are used to encode an instruction or immediate value and the four buttons are used to cycle the display, reset the machine, load an instruction into the instruction register, and execute the current instruction. There are simply no available inputs to handle inputting a series of instructions to execute. The problem of the FSM design is that we have used up all of the 4-bit state label encodings. Extending the label to 5 bits would require a reconversion to truth table. The solution to both problems is fairly trivial, but would require significant time investment into redesigning nearly all of the control logic.

## How to use

In order to view in the Xilinx ISE do the following in your terminal

````
git clone https://github.com/BaldomeroVargas/Simple-Processor.git
cd Simple-Processor
tar -xvf Xilinx Files.tar
````

After the terminal commands, open the 'manzana_uno.xise' in the Xilinx ISE software.

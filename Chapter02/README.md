## Know the Concepts 
- Describe the fetch-execute cycle. <br>
    <ol>
    <li>Fetch: The CPU retrieves an instruction from the memory location pointed to by the program counter (PC).</li>
    <li>Decode: The instruction is decoded to determine the required actions and memory locations to be used. </li>
    <li>Execute: The decoded instruction is sent to the Arithmetic and Logic Unit (ALU) or other necessary components for execution.</li>
    <li>Write Back: The result of the operation is placed on the data bus and written back to memory or a register.</li>
    </ol>
- What is a register? How would computation be more difficult without registers? <br>
    &emsp; Registers are small, fast storage locations within the CPU. Without registers, computation would be  much slower because the CPU would need to constantly access the main memory for every operation.
- How do you represent numbers larger than 255? <br>
    &emsp;With multiple bytes.

- How big are the registers on the machines we will be using? <br>
    &emsp;The size of a word. For exemple, in 32-bit system, registers are typically 32 bits wide. 

- How does a computer know how to interpret a given byte or set of bytes of
memory? <br>
    &emsp;It doesn't, unless the bytes are placed in special pourpose registers. 

- What are the addressing modes and what are they used for? <br>
    &emsp;Addressing modes are techniques used by the CPU to access data stored in memory. Few of the addressing modes include: immediate mode, register addressing mode, direct addressing mode, indexed addressing mode, indirect addressing mode, base pointer addressing mode.

- What does the instruction pointer do? <br>
    &emsp;Instruction pointer is a special-purpose register that points (holds the address) to memory locations that represents the next instructions to be executed.  

## Use the Concepts
- What data would you use in an employee record? How would you lay it out in
memory? <br>
    ```C
    register Employee { // Start of record 
        int id; // Start of record + 4 bytes 
        char *title; // Start of record + 8 bytes 
        char *first_name; // Start of record + 12 bytes 
        char *last_name; // Start of record + 16 bytes 
        float salary; // Start of record + 20 bytes 
    }

- If I had the pointer the the beginning of the employee record above, and wanted
to access a particular piece of data inside of it, what addressing mode would I
use? <br>
    &emsp;Indexed addressing mode

- In base pointer addressing mode, if you have a register holding the value 3122,
and an offset of 20, what address would you be trying to access? <br>
    &emsp; (3122 + 20) = 3142
- In indexed addressing mode, if the base address is 6512, the index register has a
5, and the multiplier is 4, what address would you be trying to access? <br>
    &emsp; (6512 + (5*4)) = 6532
- In indexed addressing mode, if the base address is 123472, the index register
has a 0, and the multiplier is 4, what address would you be trying to access? <br>
    &emsp; (123472 + (0*4)) = 123472
- In indexed addressing mode, if the base address is 9123478, the index register
has a 20, and the multiplier is 1, what address would you be trying to access? <br>
    &emsp; (9123478 + (20*1)) = 9123498

## Going Further
- What are the minimum number of addressing modes needed for computation? <br>
    &emsp; Three: direct addressing mode, immediate addressing mode and register addressing mode.
- Why include addressing modes that aren’t strictly needed? <br>
    &emsp; Easier to code. 
- Research and then describe how pipelining (or one of the other complicating
factors) affects the fetch-execute cycle. <br>
    &emsp; Instruction execution is divided into many parts, each one handled by a dedicated piece of hardware. Pipelining allows a trade-off between latency (how long it takes to execute an instruction), and processor bandwidth (how many MIPS the CPU has).
- Research and then describe the tradeoffs between fixed-length instructions and
variable-length instructions. <br>
    &emsp; Fixed-lenght instructions have the benefit of simpler decoding, but less flexibility and may require more memory, as some instructions will be larger than required. <br>
    &emsp; Variable-leght instructions have the benefit of more flexible and compact instruction set, but complex decoding.

## Virtual Memory Manager

The Virtual Memory Manager has two main duties: to create and manage address maps for processes and to control physical memory allocation.
  - This project consists of writing a program that translates logical to physical addresses for a virtual address space of size 2^16 = 65, 536 bytes. this program will read from a file containing logical addresses and, using a TLB as well as a page table, will translate each logical address to its corresponding physical address and output the value of the byte stored at the translated physical address. The goal behind this project is to simulate the steps involved in translating logical to physical addresses.
  - This program will read a file containing several 32-bit integer numbers that represent logical addresses. However, it need only be concerned with 16-bit addresses, so it must mask the rightmost 16 bits of each logical address. These 16 bits are divided into (1) an 8-bit page number and (2) 8-bit page offset. Hence, the addresses are structured as shown in the figure:

Part 1
  - In a slight departure from what is described in the assignment below, your program should run as follows: ./part1 BACKING_STORE.bin addresses.txt
  - This should produce an output file correct.txt, which shows the address translation of each address. 
  - Look through the provided correct.txt file for the specific format. 
  - Memory is large enough to accommodate all 256 pages from the BACKING_STORE.bin. That is, there is no need for page replacement. 
  - The solution uses FIFO replacement for TLB updating. 
  
Part 2
  - Due to the additional constraints added, for part 2, program should run as follows ./part2 BACKING_STORE.bin addresses.txt strategy
  - Strategy can be fifo (First In First Out) or lru (Least Recently Used). As above, the name of the output file should be correct.txt, and has the same output format as part 1. 

### 1.1 Compile and Run

a/ To run the program in folder part1:

make
./part1 BACKING_STORE.bin addresses.txt 

Then the output will be in the correct.txt

run ./part1.out BACKING_STORE.bin addresses.txt for having output in correct.txt

b/ To run the program in folder part2:

make
./part2 BACKING_STORE.bin addresses.txt fifo

or 

make
./part2 BACKING_STORE.bin addresses.txt lru

Then the output will be in the correct.txt

run ./part2 BACKING_STORE.bin addresses.txt lru 
or   ./part2 BACKING_STORE.bin addresses.txt fifo for having output in correct.txt

Check the differ between 2 files with: diff correct.txt correct2.txt

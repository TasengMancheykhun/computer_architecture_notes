* Computer
  * Main components
    * Memory subsystem
    * Input/Output subsystem
    * CPU
  
  * Program Execution
    * Stored Program
      * Idea of stored program proposed by John Von Neuman
            
 * Computer Architecture 
  * Structure of a computer
  * Instruction set of a computer
    * Instruction set = Language of a computer
    * Different CPU family = different instruction set
    
    * Binary Language
    * Assembly Language: English equivalent language
    * Assembly language will get converted to binary language.

  * Designing a computer: Before designing a computer, following things need to be taken care of:
    * Computer Performance requirements
      * Computer Performance measured by:
        * For individual computer:
          * Response time or Execution time = Time at the end of the task - Time at the start of the task 
        * At an overall level:
          * Throughput or Bandwidth
          * Bandwidth: The maximum amount of data packets or information that can be transferred per ssecond
          * Throughput: The actual amount of data packets or information that gets transferred per second 

        * Computer Performance = 1/(CPU Execution time)
        
        * Clock cycle = Time taken to complete a clock cycle = Time period
        * Clock speed or clock rate = 1/Clock cycle
        * Clock speed = Number of clock cycles per second 

        * CPU execution time for a program = Number of CPU clock cycles for the program/Clock rate

    * Interconnection between various parts of a computer
    * Defining the instruction set. Must be simple 
    
  * CISC Architecture: Complex Instruction Set Computer
    * Eg: Intel
  * RISC Architecture: Reduced Instruction Set Computer
    * Prefered by many
    * Eg: ARM

  * Fetch-Decode-Execute Cycle
    * Program execution happen line-by-line
    * CPU fetch the instruction from RAM 
    * CPU decode the instruction
    * CPU execute the instruction
    
* Computer Bus
  * A communication link (set of wires) used inside a computer to send data, addresses, control signals, and power to various hardware components of the computer.  
  * Main bus types: 
    * Address bus: (Unidirectional) Only CPU can send to RAM, Used for specifying memory address for reading or writing of data.
    * Data bus: (Bidirectional) contains data to be written or data to be read
    * Control bus: (Bidirectional) Specifies the operations, like read operation or write operation

 * Address bus + Data bus + Control bus = System bus  

 * Eg: Suppose the CPU wants to write a value of 0 in memory location 125 of RAM
   * Address bus = specifies the address of the memory location
   * Data bus = specifies the data to be written
   * Control bus = specifies the write operation

* von Neumann Architecture
  * Single memory space and single bus for data and instructions 
  * At a time either data will be sent or instruction will be sent in the bus
  * von Neumann bottleneck: Since there is only a single bus, instruction as well as data cannot be sent simultaneously, leading to von-Neumann Bottleneck due to clash of instruction and data

* Harvard Architecture
  * Separate memory space and separate bus for data and instructions
  * There are multi bus
  * Simultaneously, two memory fetches possible 
  * If two instructions can be fetched, but there is only a single instruction register (IR). Where will the other instruction be stored?? ---> at prefetch buffer
  * Harvard Architecture introduce the concept of 'prefetch buffer'
  * While one instruction is going on, other fetch instruction can happen and be stored in prefetch buffer.
  
  * Huge improvement by removing the von Neumann bottleneck and introducing prefetch buffer.
* Point-to-point connection
  * In this, every device is connected to every other device using a separate wire
  * Used in earlier times
  * Peripheral Component Interconnect (PCI)
  * Advantage: Very fast
  * Disadvantage: Huge number of wires required, adding new device increases connections, complicated

* Multi-point connection
  * A common bridge connects various devices 
  * PCI Express (Peripheral Component Interconnect Express)
  * Modern technique
  * In PCI Express: The CPU, Memory and Cache Memory are connected by a "Bridge chip"
  * Now, if we want to improve connection performance, we need to improve only this Bridge chip. In contrast to previous case where, improving connection performance is hard because altering one wire can disturb the connections.
  * Bridge chip is furthur connected to I/O devices by a 'switch'. The Advantage now is that suppose a new device is to connected. We will connect through the switch. No need to touch the Bridge chip.

  * This is called 'Loosely Connected Architecture'
    * In this architecture, We can change connections and the overall computer interaction will not be impacted
  * Tightly Connected Architecture 
    * In this one change in part of a connection will impact overall computer interaction. 

* CPU Organization
  * CPU = Control Unit (CU) + Arithmetic and Logical Unit (ALU) + Registers
    * ALU's purpose is to calulate and Register's purpose is to store
  * Registers are fast memory inside the CPU
    * Fastest type of memory because it is inside CPU
    * Purpose: Purpose is to store the informations of arithmetic and logical operations during the calculation or store temporary results.
    * What next instruction to do is also stored in register called Program Counter
   
  * Registers in x86 CPU
    * General purpose registers: AX, BX, CX, DX. 
      * Here, Size of each register = 16 bits
      * Made of two separate 8-bit registers (high and low)
      * Accumulator Register AX = AH, AL
    * Segment registers: CS, DS, ES, SS
      * Code Segement, Data Segment, Extra Segment, Stack Segment
  
  * Arithmetic and Logical Unit (ALU)
    * Performs most of the operations
    * Its purpose is to calculate
  
  * Control Unit (CU)
    * It uses Instruction Pointer (IP) or Program Counter (PC), that contains the address of the next executable instruction
    * It fetches instruction code (op code) from memory using Program Counter (PC)
    * Move the op code into the instruction decoding register (Instruction Register (IR))
    * Increment the value in IP/PC to get the next instruction after the current instruction is complete 
    * In Fetch-Decode-Execute, Fetch and Decode is done by CU. In execute, CU participates but mostly done by ALU.  
  
  * Instruction Set Architecture (ISA)
    * Every CPU understands a fixed set of machine language instructions, called Instructions set
    * Different CPU families (e.g. Intel, ARM) = Different ISA
    * i.e Intel CPU's machine language != ARM's machine language
  
  * Op Code and Operand
    * Instruction: Has two parts:
      * Op code: Operation/instruction to be performed
      * Operand: Data/value/memory location on which the op code is going to work

      * Eg: Add R2, R2
        * Add = op code, R1 and R2 - operand
        * R2 = source, R1 = destination  
        * R2 remains unchanged, R1 may get modified
     
  * Intel x86 Architecture:
    * 16 bit instruction set--> later modified to 32 bit
    * 32 bit CPU - 32 wires between CPU and main memory (Address bus = 32 bits)
    * A 32 bit CPU can access 2^32 = 4,294,967,295 ~ 4GB RAM locations at a time
    
  * Intel x64 Architecture: 
    * 64 bit architecture
    * 64 bit CPU - 64 wires between CPU and main memory (Address bus = 64 bits)
    * A 64 bit CPU can access 2^64 ~ 18.4 exabyte memeory locations at a time
    
  * **[Imp]** Overview of x86 Data Types:
    * Bit = 1
    * Nibble = 4 bits
    * Byte = 8 bits
    * Word = 16 bits
    * Double word = 32 bits
    * Quadword = 64 bits

    * 1 Byte can store number ranging from 0-255
    * 1 Word can store number ranging from 0-65,535
  
  * Addressing Modes : This decides how we identify the operand of our instruction
    * Advantage of Adressing modes: Allows more flexibility to the programmer, since the operands can be in the registers, memory, or in a memory location pointe to by another memory location
    * Drawback: More complexity in instructions

    * Types of Addressing modes:

      * Register Addressing Mode: 
        * Operands are in the CPU registers
        * Fastest
        * Eg: Program to add two numbers
          * mov ax, 03h
          * mov bx, 05h
          * add ax, bx 

      * Immediate Addressing Mode:
        * Operand is a constant
        * No memory access needed
        * Limited use
        * Eg: Program to add a constant 05 to a register ax that already contains some value 03
          * mov ax, 03h
          * add ax, 05h
      * Direct Addressing Mode:
        * Operand's memory address is used
        * Simplest
        * Slower than Register addressing mode and Immediate Addressing mode
        * Limited by register and memory size 
        * Eg: Program to add a value stored at memory address 1000 into a register
          * mov ax, 03h
          * mov [1000h], 05h
          * add ax, [1000h] 
      * Indirect Addressing Mode
        * Actual value is at a memory address, and address value is in a register
        * Complex and slower than Register & immediate & also direct addressing mode
        * Eg: Program to read the value at a memory address stored in a register 
          * mov ax, 03h
          * mov [1000h], 05h
          * mov bx, 1000h
          * add ax, [bx]
      * Indexed Addressing Mode
        * Actual value is at a memory address, and address value plus an index is in a register
        * Eg:
          * mov ax, [1000+bx] 
        * Used in Arrays, pointers, records and other data structures

  * Complex CPUs will have more addressing modes
  * Simple CPUs will have lesser addressing modes   
  

* Number Systems and Data Representation:

  * Decimal numbers, Binary Numbers, Hexadecimal Numbers

  * Reset and Carry
  * Bit
    * Binary Digit = Bit
    * One bit is stored in one transistor
    * Binary Weights:       
      * Just like in decimal number, in binary number system also, each bit has a positional weight
        * 128 64 32 16 8 4 2 1
  
  * Binary to decimal conversion: 8421 method

  * Decimal nmber to Binary Conversion
    * Divide number by 2, keep remainder

  * Hexadecimal Numbers
    * Used in Microprocessor work 
    * Much shorter than binary numbers
    * Eg: 10101101011 in binary = 56B in hex

    * Hexadecimal = Hex + Decimal
    * Digits 0 to 9 and letters from A to F 
    * Reset and Carry: 0 to 9 then A to F, then reset to 0 

  * Comparing Decimal, Binary and Hexadecimal
    * 0  0000 0
    * 1  0001 1
    * 2  0010 2  
    * 3  0011 3
    * 4  0100 4
    * 5  0101 5
    * 6  0110 6
    * 7  0111 7
    * 8  1000 8
    * 9  1001 9
    * 10 1010 A 
    * 11 1011 B
    * 12 1100 C   
    * 13 1101 D
    * 14 1110 E
    * 15 1111 F

  * Base or Radix
    * Base or radix of a number system is equal to the number of digits it has
    * Decimal number system's base is 10
    * Binary number system's base is 2      
    * Hexadecimal number system's base is 16

  * Hexadecimal to Binary Conversion
    * First convert each digit to decimal, then to binary

    * Eg: 9AF ----> 9 10 16 ----> 1001 1010 1111
    * Eg: C5E2 ----> 12 5 14 2 ----> 1100 0101 1110 0010   

  * Binary to Hexadecimal Conversion
    * Eg: 1000 1100 ----> 8 12 ----> 8 C
    * Eg: 1110 1000 1101 0110 ----> 14 8 13 6 ----> E 8 D 6
   
  * Hexadecimal to Decimal Conversion
    * Little Tedious
    * Eg: F8E6 
      * (Fx16^3) + (8x16^2) + (Ex16^1) + (6x16^0)
      * (15x16^3) + (8x16^2) + (14x16^1) + (6x16^0)
      * 61440 + 2048 + 224 + 6     
      * 63,718
    
  * Decimal to Hexadecimal Conversion
    * Eg: 63718
      * Divide by 16, Store remainder

  * Binary-coded-Decimal (BCD) Numbers
    * BCD numbers express each decimal digit directly as sequence of its four bit representation
    * Decimal to BCD conversion
      * Example: Decimal number 2945 in BCD is
        * 0010 1001 0100 0101

    * BCD to Decimal conversion
      * Directly read each four bit and write the corresponding decimal digit
      * Example:  0010 1000 0111 0100
        * 2 8 7 4

  * ASCII Code
    * American Standard Code for Information Interchange (ASCII)
    * purpose: Computers need to deal with numbers, alphabets and other symbols. But they only understand binary (0 and 1)
    * ASCII is a standard code to map symbols to binary values
    * Initially 7-bit (128 characters), but later modified to 8-bit (256 characters) (Extended ASCII)

  * Unicode (UTF)
    * Unicode is a universal character encoding standard
    * 4 byte = 2^32 characters allowed. Hence provides a very wide variety of encoding

  * **[IMP]** Binary Arithmetic

    * Binary Addition:
      * Rules of Binary Addition:
        * 0 + 0 = 0
        * 0 + 1 = 1
        * 1 + 0 = 1
        * 1 + 1 = 10      (RESET and CARRY)
        * 1 + 1 + 1 = 11

        * Eg: 11100 + 11010 = 110110

    * Binary Subtraction:
      * Rules of Binary subtraction:
        * 0 - 0 = 0
        * 1 - 0 = 1
        * 1 - 1 = 0
        * 10 - 1 = 1

        * Eg: 111 - 101 = 010 
        * 1101 - 1010 = 0011
        * Cheap trick - just convert to decimal and do the subtraction
  
  * Signed Binary Numbers:
    * Also called sign-magnitude numbers
    * Used to represent Negative decimal numbers. Eg: -5, -57, -78, +98, etc
    * For binary numbers,
      * positive sign is 0
      * negative sign is 1
      
    * In binary 
      * 0001 means +1 
      * 1001 means -1
      * 0010 means +2
      * 1010 means -2 

  * 2's Complement
    * 2's complement = 1's complement of a number + 1 
    * Advantage of 2's complement:
      * Sign-magnitude numbers need separate hardware for binary addition and subtraction. But with 2's complement, we can use a simple digital ciruit to perform both addition and subtraction.

      * Sign-magnitude numbers has two zeroes (e.g. 000 is +0 and 100 is -0)

  * How are Characters stored in Memory? 
    * A - Z = 65 - 90 (ASCII value / Decimal Number system)
    * a - z = 97 - 122 (ASCII value / Decimal Number system)
    * Each character is stored using its 8-bit ASCII representation in binary
      * Eg: ASCII code for character c : 99 (decimal) = 01100011 (binary)

  * Positive Integers
    * 4 bytes (32 bits) per integer
      * 1st bit for sign, remaining 31 bits for value
    * Eg: Integer 65 is stored in memory as binary,
      * 00000000 00000000 00000000 01000001
    * Most Significant Bit (MSB), here is 0, since the number is Positive   

  * Negative Integers
    * 4 bytes (32 bits) per integer
      * 1st bit for sign, remaining 31 bits for value
    * Eg: Integer -65 is stored in memory as binary,
      * 65 in 32-bit binary = 00000000 00000000 00000000 01000001
      * 2's complement = 11111111 11111111 11111111 10111110 
      * Most Significant Bit (MSB), here is 1, since the number is Negative

  * Floating Point Numbers Storage in Memory
    * 4 bytes (32 bits) 
    * Eg 1: 4.25 ----> has two parts: Integer part (4) and Fractional part (0.25)
      * Integer part: Convert 4 to binary 4 = 100
      * Fractional part: 0.25
        * Multiply fractional part with 2 until it becomes 1.0
        * 0.25 * 2 = 0.50 ----> Take 0 and move 0.50 to next step
        * 0.50 * 2 = 1.00 ----> Take 1 and stop the process as there is no remainder
        * Hence, 0.25 = 01
      * Lastly, 4.25 = 100.01

    * Eg 2: 10.75:
      * Integral part: 10 = 1010
      * Fractional part: 
        * 0.75*2 = 1.50 ----> Take 1 and move 0.50 to next step  
        * 0.50*2 = 1.0 -----> Take 1 and stop the process as there is no remainder
        * Hence, 0.75 = 11
      * Lastly, 10.75 = 1010.11

    * A floating point number is stored in memory as made up of three parts:
      * Sign
      * Exponent
      * Significant Value

    * Normalized form
      * 10.75 = 1010.11 = 1.01011 * 2^3

      * We need to add bias to exponent
        * bias = $2^{n-1}-1$
        * n = Number of bits for exponent = 8
        * bias = $2^{8-1}-1$ = 127

      * The normalized exponent is: 3+127 = 130
      * Binary form of 130 is 10000010

      * Sign bit = 0, because 10.75 is positive
      * Exponent = 130, which is 10000010
      * Significant value = 1.01011. Taking only the part after the dot, i.e, 01011

      * Hence, 10.75 is stored as 
      * 0 10000010 01011000000000000000000
      * 32bit = 1 bit + 8 bit + 23 bit 

      * And, -10.75 is stored as 
      * 1 10000010 01011000000000000000000
      * 32bit = 1 bit + 8 bit + 23 bit 

* Memory
  * Memory Classification
    * RAM 
      * SRAM (Static RAM)
        * Used as cache memory
        * Does not need to be constantly refreshed  
        * Has faster data access time 
      * DRAM (Dynamic RAM)
        * Needs to be constantly refreshed 
        * Has less faster data access time

    * ROM  
      * PROM
      * EPROM
      * EEPROM

  * Memory Hierarchy
    * Registers: 1 nsec [Fastest access, Most expensive], <1KB 
    * Cache: 2 nsec, 4MB  
    * Main memory: 10 nsec, 1-8 GB 
    * Magnetic Disk: 10 msec [Slowest access, least costly], 1-4 TB
  
  * Cache Memory is placed between CPU and Main Memory

  * Memory Interleaving
    * Improve memory access performance by distributing data across multiple memory modules or interleaves
    * Example: If we have 2 memory modules, the memory space might be divided into two interleaves: Interleave 0 and interleave 1
    * Uses round robin algorithm
    * Parallel memory access possible
    * Useful in multi-core processors

    * Example: Suppose we have 4 interleaved memory modules
      * Module 0 contains memory addresses 0, 4, 8, 12, 16, ...
      * Module 1 contains memory addresses 1, 5, 9, 13, 17, ...
      * Module 2 contains memory addresses 2, 6, 10, 14, 18, ...
      * Module 3 contains memory addresses 3, 7, 11, 15, 19, ... 

    * Advantage of Memory Interleaving: The CPU can read memory modules one after the other quickly to access data. 

  * Paging
    * When the Process memory requirement is larger than the physical capacity of the RAM (Physical address space), the process address space is divided into smaller parts (called as Page), such that only one of these parts is loaded into the RAM at any time.
    * This technique is called Paging.
    * The physical memory RAM is divided into *page frames*
    * Page table or Page map table: Maps virtual address to physical address.
    
  * Virtual Memory
    * It is the result of paging
    * Now the virtual memory is much more than its real physical capacity
    * In the virtual memory, the process memory is divided into *virtual pages*
    * Some virtual pages are loaded into page frames and the remaining ones are in the secondary memory  
  * Page Replacement
    * *Page fault*: Program refers to a virtual memory address that is not present in the physical/real main memory
    * Eg: If say 'main' function is loaded in the RAM, but CPU wants to use 'calculate' function which is not loaded in the limited RAM. This is called Page fault.

    * *Working set*: Set of pages that a program is actively and heavily using

    * *Page replacement policy*: 
      * Decides how to handle page faults
      * Least Recently Used (LRU): Swaps out the page least recently used
      * First In First Out (FIFO): Removes the first loaded page

    * *Thrashing*:
      * Repeated page faults occuring

    * *Demand paging*:
      * Only load pages on demand, not in advance

    * *Dirty bit*:
      * Dirty bit tells the OS if any page frame in the RAM has been modified. Dirty bit becomes 1 when modified, else 0. Dirty bit makes sure changes are not lost in the event of page replacement.

 * Associative Memory:
   * Also called Content-Addressable Memory (CAM)
   * Allows data to be retrieved based on its content rather than its specific memory address
   * Search keywords/patterns, instead of providing memory address
   * Used in cache memory, network routers and applications where fast search is needed.    

* Networking
  * Communication System 
    * Components
      * Source - Transmitter - Transmission Channel - Receiver - Destination
      
      * Eg: Workstation - Modem - Public Telephone Network - Modem - Server
    
    * Issues in communication Networking
      * Bandwidth Limitation
      * Latency
      * Packet Loss

  * Network Types
    * PAN
    * LAN
    * MAN
    * WAN
    * Internet

  * Network Topology: Represents a network arrangement consisting of several nodes 
    * Bus Topology
      * All nodes connected to a single wire (called a bus)
      * Simple and effective but not fast
      * All depends on a single wire 
    * Ring Topology
      * Multiple computers, one connected to the next to complete a ring
      * A transmitting computer needs to have a token before transmitting
      * Inexpensive
      * Tough to add or remove nodes, One node crashing can disconnect the whole network  
    * Star Topology
      * Each computer is connected to a central hub
      * All commpunication goes through the hub only
      * Simple but too much dependence on the hub
      * But the hub can be upgraded easily. Easy to troubleshoot, Cost is high 
    * Mesh Topology 
      * All nodes are connected to each other
      * Very robust, Easy to diagnose errors, privacy and security are better
      * Costly, Too much of wiring   
    * Tree Topology
      * Nodes are connected hierarchically, ultimately connecting to the top node, called as root node
      * Has atleat 3 levels of hierarchy
      * Easy to expand and manage, debug
      * Expensive, lots of cabling        
  * Network Interface Card (NIC)
    * Also called LAN card
    * Interface between a computer and a network
    * Has hardcoded address: MAC address, Physical address, Hardware address

  * Wired LAN technologies
    * Ethernet
      * Ethernet Generations:
        * Classic Ethernet (Bus topology)
        * Gigabit Ethernet/Switched Ethernet (Star topology)  
      
    * Token Ring
    * Token Bus
     
  * Transmission media
      - Carries information from a source to a destination
    * Media:
      * Guided media: (Wired)
        * Co-axial cable (uses electric current)
          * coax carries signals of higher frequency ranges than those in twisted-pair cable
          * coax has a single copper wire, instead of two wires
          * Eg. Telephone, cable TV, LAN  
        * Twisted-pair cable (uses electric current)
          * UTP (Unshielded twisted-pair)
          * STP (Shielded twisted-pair)
        * Fiber optics (uses light) 
          * Made of glass or plastic and transmits signals in the form of light
          * Modern ethernet is fibre optic based 
      * Unguided media: (Wireless)
        * Uses electromagnetic waves. Signals are broadcasted through free space
        * Electromagnetic spectrum region ranging from 3kHz to 900 THz
        * Two types: 
          * Infrared
          * RF

  * Protocol 
    * Set of official/implicit rules used for communication between two devices        
    
    * OSI - Open Systems Interconnection
      * Sometimes also called ISO/OSI 
      * Contains 7 layers
        * Application Layer *(layer 7)*
          * HTTP(access web pages), SMTP (Email), FTP (file transfer), DNS (Querying domain names)
          * Encapsulation begins here
        * Presentation Layer *(layer 6)*
          * Translation: Encodes to common format to take care of differences  
          * Encryption: To achieve confidentiality or privacy
          * Compression: Reduces the number of bits needed to be transmitted
        * Session Layer *(layer 5)*
          * Manages the session between applications
          * Eg: Between browser of the source computer and server of the destination computer
        * Transport Layer *(layer 4)*
          * Identifies the application on the destination computer using port numbers
          * Eg: One server, multiple applications: FTP, Telnet session, Webpage 
        * Network Layer *(layer 3)*
          * This layer uses IP address to send information
          *General Info about IP and MAC address*
          * Sender and receiver in the same network use MAC addresses
          * Sender and receiver in different networks cannot use MAC addresses. So they need to use IP address
          * MAC address: S---[switch]---R
          * IP address: S---[switch]---[Router]---[Router]---[switch]---R 
          * Each computer has two types of addresses:

            * MAC address/Physical address/Hardware address
              * Fixed address, Hardcoded on the Network Interface Card(NIC)
              * Different for different network type (Eg. Ethernet card, WiFi card) 
              * Useful within or inside a network
 
            * IP address/Logical address/Virtual address
              * Given by the network provider or your organisation
              * Usually temporary
              * Useful outside a network (e.g. to reach another computer on the internet, anywhere in the world)

        * Data Link Layer *(layer 2)*
          * LAN/WAN operates at this layer (eg. Ethernet or Wifi)
        * Physical Layer *(layer 1)*
          * carries the data (0s and 1s) in the form of signals
          * Signals can be electric, optical, or wireless
    * Port Numbers  
      * Port number is a 16-bit value, So it can store 2^16=65536 digits i.e 0 to 65535
      * Three types:
        * Well-known ports: 0-1023 - used in server
        * Temporary/Ephemeral: 1024-49151 - used in client
        * Dynamic, Usage-based: 49152-65535
     
    * TCP/IP protocol suite
      * Came before OSI 
      * Has 4 layers, not 7
        * Application layer *(layer 4)*
          * Telnet, HTTP, SMTP, FTP, DNS, SSH 
        * Transport layer *(layer 3)*
          * TCP (Transmission Control Protocol)
            * Reliable protocol
            * Gauranteed delivery
            * Uses connections, acknowledgements
            * Used for text-based data
          * UDP (User Datagram Protocol)
            * Unreliable protocol
            * No guarantee of delivery
            * No connections, no acknowledgements
            * Useful for audio, video or wherever we need speed but not guarantee
        * Internet layer *(layer 2)*
          * Eg: IP, ICMP, ARP, DHCP
          * Provides logical addressing (IP addresses)
          * Performs routing
          * Provides an IP datagram format

          * ARP (Address Resolution Protocol)
            * Sender knows the IP address but not the MAC address. Request will be broadcasted to every computer when searching for IP address
            * Input: IP address of a computer, Output: its MAC Address

          * ICMP (Internet Control Message Protocol) 
            * This protocol helps IP deal with problems.
              * IP is connectionless
              * Unreliable
              * Unacknowledged
            * Suppose Machine A sends a packet to Machine B, and Machine B is down. A router that is connected to B knows this and discards the packet sent by A, and informs A to stop sending packets through ICMP protocol.  
            * ICMP Message types: 
              * Error-reporting messages: Used to report problems
              * Query messages: Ping command to test the connection and gain information
                * Ping = Computer A sends test packets and computer B acknowledges

          * DHCP protocol (Dynamic Host COnfiguration Protocol)
            * Machine has fixed MAC address but not fixed IP address
            * Machine will send out a request that my MAC address is this, can anybody allot me an IP address. The DHCP server will allot the machine an IP address through the DHCP protocol. 

          * IP Address
              * dotted decimal notation
              * Has two parts: Network Id and Host Id 
              * classful addressing: Means some portion of the network id is reserved to indicate class of IP address
              * IP address: total 8 bits x 4 = 32 bits
                * first bit
                * class A = 0-127
                  * min 00000000, max 01111111
                * class B = 128-191
                  * min 10000000, max 11111111
                * class C = 192-223
                  * min 11000000, max 11111111   
                * class D 
                * class E    
                
              
        * Network Access *(layer 1)*
          * Ethernet, PPP, ADSL
    
  * Networking devices     
    * To connect devices within a network, by use of MAC addresses
      * Hub ---> layer 2 device (Data link layer) 
      * Switch ---> layer 2 device (Data link layer)

    * To connect devices from different network, by use of IP addresses
      * Router ---> layer 3 device (Network layer)

    * Hub
      * 
    * Switch




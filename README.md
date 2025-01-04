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
  * Single memory and single bus for data and instructions 
  * At a time either data will be sent or instruction will be sent in the bus
  * von Neumann bottleneck: Since there is only a single bus, instruction as well as data cannot be sent simultaneously, leading to von-Neumann Bottleneck due to clash of instruction and data

* Harvard Architecture
  * Separate memory and separate bus for data and instructions
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




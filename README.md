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
              
        * Network Access *(layer 1)*
          * Ethernet, PPP, ADSL
    
    *   

# Course Plan

1. [Hardware](#hardware)
2. [Internet](#internet)
3. [Multimedia](#multimedia)
4. [Security](#security)
5. [Web Development](#web-development)
6. [Programming](#programming)


## Hardware

###  Binary
- **Numbers can be represented in different bases**
    - F.e. in decimal with digits from 0 to 9. $$123_{10} = 1 * 10^2 + 2 * 10^1 + 3 * 10^0$$
    - Or in binary with 0s and 1s. $$10101_2 = 1 * 2^4 + 0 * 10^3 +  1 * 2^2 + 0 * 10^1 +  1 * 2^0 = 21_{10}$$
    - So same numbers can be represented in different forms: $$5_{10} = 101_2$$
- **Computer can store only binary numbers. Why?**
    - Easier to create two state systems
        - light bulb in first computers
        - transistors in modern
    - Bulb/Transistor is turned on = **1**; turned off = **0**
- **But how to get characters? => Encoding = mapping a number to a character**
    - ASCII - 7-8 bits ~ 256 characters - not enough for different languages.
        - 65 = 'A'
        - 97 = 'a'
    - UNICODE
    - UTF-8/16/32

### CPU - Central Processor Unit
- Attached to **motherboard** - silicon circuit board
- **The Brain of the computer**
    - Operations:
        - performes math operations
        - displays numbers on the screen
        - save info to memory and load from memory
    - Now can have several **cores** - do several tasks simultaneously
    - Also can support **multithreading**
        - One core behaves as several for OS
- Examples of monolit computers (not on motherboard)
    - Raspberry PI
    - Phones, tablets, game consols
- 2-4 GHz - billion operations per sec

### RAM - Random Access Memory
- **Fast memory of the computer**
    - Digital storage (circuit)
    - Works only with electricity
    - Load necessary data to quickly operate with it
- 1-32 GB

### HDD - Hard Disk Drive
- **Slow memory of the computer**
    - Physical Storage
        - Disk with magnetic particles with 2 polarization states: 0s and 1s
        - Reading heads moves back and forth to read and write data
        - RAM sends data to HDD and HDD translates it to fluctuation of voltage. 
        - If dropped can lose data
    - Need a special place (file) that tracks data's location
    - Don't need electricity to store data
- 256 GB - 2 TB

### Flash Memory - SDD - Solid State Disk
- Smaller and much faster than HDD  
- Can store without electricity but theoretically for less time than HDD
- 1-512 GB
- Hybrid Disks - SSD for frequently-used data and HDD for less frequently-used data

### Memory Funeling
- HDD(TB) -> RAM(GB) -> L3(MB) -> L2(MB, KB) -> L1(KB) cash -> CPU
- **L1-L3 cashes** used to fastly exchange data with CPU
- **Registers** - store number for operations

### Display Connectors
- Different Display connectors are used to connect various monitors to a computer
- HDMI, VGA

### USB - Universal Serial Bus
- USB connectors used to connect devices (keyboard, mouse, printers, etc.) to a computer
- USB-A/B/C
- Connectors use protocols to exchange data between devices/monitors and computers

### Wireless
- Wifi - internet connection
- Bluetooth - for devices - limited range

### OS - operating system
- Interface between hardware and software
- Stored in HDD or SSD and loaded to RAM when the computer is turned on
- Provide communication between devices
    - Drivers - software that works with certain devices
- Gives graphical interface


## Internet

### Introduction
- ISP - Internet service provider - give to us an access to the internet for a month fee.
- Internet - network of networks of computers
- Allows us to communicate with each other

### IP - Internet Protocol
- For communication we have to know where to send data. So we need address
    - IPv4 address #.#.#.# where # [0, 255]
        - Address can be configured physically
        - DHCP servers can do it automatically
            - When you connect to the ISP router, you make a request to DHCP server to get an IP address
        
### DNS - Domain name system
- We communicate with websites by domain names (google.com, facebook.com etc.) but they also have an IP address.
- DNS server converts domain name to IP address.

### Packets
- Computer communicates via packets of 0s and 1s
- When we make a request we need and address and data
    - Then ISP helps to send your data to the receiver
        - If address given by domain name ISP searches it in different DNS servers 'til root server.
    - After request we'll later get a response
- Data can weigh a lot so it divided into more different packets (fragments).

### TCP/IP
- IP - protocol - rules how data should be transferred
    - supports fragmentation above
- But a packet can be lost so TCP/IP
- TCP - protocol that ensures packets get to their destination
    - If some packet is missing -> make a request for this packet
    - Includes port - identifier of service.
        - So f.e. google knows we're requesting a webpage not an email

### PORTS
- As said above - port identifies service
- F.e. 
    - 80 - http - protocol for web servers communication
    - 443 - https (ssl)
    - 25 - email


### Protocols
- Protocol - set of rules how to communicate

### UDP - User Datagram Protocol
- Don't guarantee delivery
    - Anytime you want data keep coming without waiting for a buffer to fill.
    - F.e. used for video calls and broadcasting

### IPs in more detail
- IP addresses
    - Local IPs
    - Subnet Mask - check if the same local network
    - Gateway
    
### Routers
- Routers are devices that store tables with IP addresses and where to route a packet further
- There can be several paths from A to B and each packet can go through any of them.

### Traceroute
- Traceroute (tracert windows) is a program that sends packets to each router on path and gets time to reach them.

### Undersea cabels
- To transmit data between continents we have undersea cabels

### Demos
- Modem
    - Ethernet RJ45
    - RJ11 for phone
    - Coax for TV
- Switch
    - Connecting multiple devices
- Router


## Multimedia
- File format - a way to store 0s and 1s so a particular software can interpret it
- Compression - reduce an amount of 0s and 1s after some operations (f.e. cutting of frequencies in music that we cannot hear)
- Metadata - invisible for user data which is used by software to interpret a file.

### Audio
- Formats
    - WAV - no compression
    - MP3, AAC - compression
    - MIDI
- Sampling Frequency * Bit Depth = size of one second of audio file
- Streaming services pass bits not files

### Graphics
- Simple just 0s for black and 1s for white
- We need to determine a mapping
- Formats
    - BitMap (.bmp) format
        - [RGB](#but-how-to-store-color-rgb) color = 24 bits for a pixel
        - Sometimes a lot of repeated colors => [compression](#compression)
    - GIF - low quality image (8 bit colors)
        - Can store several images for animation
    - JPEG
    - PNG
- There is no way to enhance an image like in films.
- Image Compression
    - losslessly - example with repeated colors
        - We can have a col with colors for a row and if in the row there is another colors, change them.
    - lossy - can be used with approximation of a color (f.e. make 4 pixels to 1 by averaging color)


#### But how to store color? RGB
- RGB - Red Green Blue
    - We can decide how much red green and blue we want in our color. It can be represented by a number (0-255 - 8 bits for a color)
    - Color are usually represented as hexadecimal numbers (0-9 A(10)-F(15)). One hexadecimal = 4 bits so:
        - \#FF FF FF = <span style="color:#ffffff;background-color:black">White</span>.
        - \#00 00 00 = <span style="color:#00ff00">Green</span>.
        - \#FF 00 00 = <span style="color:#ff0000">Red</span>.

### Video
- A container that stores:
    - audio tracks
    - video track: a bunch of images that are showed at high rate (>24 per sec).
- Video Compression
    - Same as images for each frame
    - Store only key frame and differences in next frames (f.e. no need to store same background in each frame)
- Formats
    - Codecs
    - MP4
    - AVI

### 3D video
- 360 degree image can be stored in 2D like map of a globe


## Security
- How to defend your data.

### Privacy
- Do not allow physical access to your personal data

### Deleting a file
- File deletion doesn't clear space on HDD.
    - OS have file that stores locations of other files
        - Deletion simply forgets about file's location
            - WHY?
                - Forgetting location is much faster than wiping out the disk
                - To protect from accidental deletion (recycle bin + stays on HDD)
    - So file can be restored by using special software

### Internet Browser
- Cookie - information that is set up on a user's browser by the website.
    - F.e. for website to understand that you're logged in
    - **Encrypted** so it's not easy for hacker to use it
    - Stored in a database
    - Sent by browser to webservers
- Browser History
    - anyone who has an access to the browser can get its history
- Both can be cleared

#### Incognito Mode
- Helps to test websites to model a new user
- Do not save a history

### Passwords
- Do not use common phrases and words
- Possibilities
    - 0-9: 4 digit code ~ 10000 possibilities
    - a-zA-Z0-9: 4 digit code ~ 62^4 = 14,776,336 possibilities

#### Reseting
- Password should be encrypted or hashed on the website side so nobody except you can know the password.
- So the website shouldn't just send you your password
    - Usually it's considered that you have an access to your email
        - Websites send a reseting password link to user's email

#### Same password
- Using the same password for different websites convenient but not secure.

#### Password managers
- A software that can generate and store long passwords for you to not remember them
- Have master password to get access to other passwords
    - Forgetting it means you lost your accounts

#### Two factor authentication
- One factor is a password
- Second factor can be
    - Special device synced with a webserver that shows second factor (some number)
    - Phones with software that do the same
    - sms or email code

### Network Security
- public wifi
    - http vs https
    - **VPN**
        - encrypted connection.
        - communcate with you and with webserver you want to visit

### Firewall
- Looks at IP addresses and helps keep bad guys out and user data inside.

### Encryption
- Somehow scrambling data
- Basic Caesar cypher
    - rotational cypher 

### Public Key Cypher
- Two keys: public and private
    - public key to encrypt
    - private to decrypt
- Ordinary used to exchange some secret key

### Phishing
- Using emails with links to wrong website in order to steal your data (f.e. password)

### Malware
- Same way someone can send you malware via email
- Ransomware can encrypt your data and ask for money to decrypt it
- Malware can do anything with your computer

### Trust
- Any security system build on trust.
- You choose who you want to trust
- Website can do things that they aren't claim


## Web Development

### [Internet](#internet)
- Computers interconnection supports HTTP and TCP/IP technologies.

### HTTP
- In the internet we communicate by sending http requests and receiving http responses
    - Web Browser - software that contains space for writing URL (Uniform Resource Locator) in order to make a request.
    - Web Server - a computer (CPU, RAM, HDD) that can receive request and response accordi ngly.
- HTTP Status Codes
    - 200 Ok
    - 404 Page not found
    - others
- HTTP methods
    - GET
        - ? parameters

### HTML
- HTML - HyperText Markup Language for webpages
    - tag based
        - tags can have attributes
            - (f.e. \<a>\</a> have *href* attribute)
- DOCTYPE
- Tag list
    - html
    - head - metainformation
    - body - webpage
    - a - anchor (links)
    - img
    - p - paragraphs
    - h1-h6 - headings
    - ul | ol (unordered, ordered lists)
        - li - list item
    - table
        - tr - table row
        - td - table data
    - form
        - input
- **curl cmd program** to make requests
    - \-I flag
- DOM tree
- Simple HTML
```HTML
<!DOCTYPE html>
<html>
    <head></head>
    <body>
        <a href="https://google.com">google</a>
    </body>
</html>
```

### CSS
- CSS - Cascading Style Sheet - used to style webpage
- Can be put:
    - directly in HTML tags using **style** attribute of any tag
    - in **style** tag
    - In separate css file that can be included in html header via **link** tag
- CSS consist of:
    - selector - tag, class, id
        - properties: values
- Properties list
    - text-align
    - font-size
- CSS styles are passed down through the DOM tree.
- Simple CSS
```CSS
body {
    text-align: center;
    font-size: 16px;
}
```

### Deployment
- People can see your website only if you deploy it on some webserver
- Web host and Domain name can be paid and then website can be placed on the web host.


## Programming
- Programming - creating software that runs on hardware
    - implementing algorithm, sequence of actions, by coding
- Pseudocode - algorithm in english
- Programming structures
    - Loops
    - Conditions
    - boolean expressions
    - Variables
    - Functions
    - threads - two things happen simultaneously
    - events - intercommunication tool between code blocks
- Programming languages
    - C/C++ - example of compiled language (compilation - creating machine code)
    - Python - example of interpreted language (interpreter - program that runs code)
    - Java, Ruby, Lisp, JavaScript
- Scratch example (with GUI for kids)
    - Building blocks
    - Sounds/Loops/Animation
- Breaking down problems!
    - Segmentation of task
- Types of programming
    - OOP
    - Functional
    - Procedural

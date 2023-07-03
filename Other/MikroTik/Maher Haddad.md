# What is MikroTik?

- Router software and hardware manufacturer
- Products used by ISPs, companies and individuals
- Make Internet technologies faster, powerful and affordable to wider range of user

### What is RouterOS?

- RouterOS is a stand-alone operating system based on the Linux kernel
- The operating system of RouterBOARD
- Can be also installed on a PC
- RouterOS is an operating system that will make your device:
  - a dedicated router o a bandwidth shaper
  - a (transparent) packet filter a (transparent) packet filter o any 802.11 a , b, g, n and ac wireless device
  - And much more

### What is RouterBOARD?

Hardware created by MikroTik - Range from small home routers to carrier-class access concentrators.

### Integrated Solutions

- These products are provided complete with cases and power adapters.
- Ready to use and prefigured with the most basic functionality.
- All you need to do is to plug it in and connect to the Internet or a corporate network

### FIRST TIME ACCESS - QUICK SET layer 3

1. Set an IP on your PC of 192.168.88.2/24
2. Connect to the MikroTik router on port Eth2 from your PC (It is blocked on Eth1)
3. Ping from your PC to 192.168.88.1. Do it work?
4. Go to the browser and type on the URL the following IP: 192.168.88.1
5. Check the quick set settings on the router //change country as your own to use the right country power.
6. Go to the WebFig and check the configurations that is pre-configured on the router from the quick set profile (home ap and ...)
7. Reset the configuration from WebFig by not having any default configuration
8. Are you able to get access to the router on the browser again? Why not? no Because we have fully resets the router.

## mikrotik winbox layer 2

1. Go to https://mikrotik.com/download and download Winbox
2. Open Winbox and go to Neighbors. What do you see?
3. Connect to the Router MAC address using username admin and password blank
4. Set an IP address on Eth2 of 192.168.88.1/24
5. Set an IP address on your PC of 192.168.88.2/24 (next step is going back to layer 3)
6. Ping from your PC to the router, do you have a reply?
7. Connect now on the IP address from Winbox. Does it work?

## CONNECTING VIA TELNET port 23 (not secure) AND SSH port 22

1. Go to https://www.putty.org/ and download the binary file of putty
2. Open putty and make telnet connection to RI
3. Change the name of RI to R2. Does it change if you check on Winbox?
4. Close the telnet session and open an SSH session to the router
5. Change the name of R2 to RI. Does it change if you check on winbox?

## Introduction to the cli with command line

1. Open new Terminal on winbox and click on tab. What means the blue(can be used solo) and purple words(needs command after it)?
2. Write sys followed with a tab. What you get?
3. Make a question mark then a tab after the word system, what is the difference?(gives more information)
4. Write system identity and click enter.Then write ping 8.8.8.8, does it work? If not solve the problem.
5. Keep the ping open. How to stop it?
6. Go to the root level and enable the hotJock by pressing ctrl+v. Check what this mode can do.
7. Go to the root mode and do double tab.What do you see?
8. Close the terminal without using the mouse

## connecting the mikrotik router and the pc to the internet

1. Go to winbox. IP then DHCP client and select the interface Eth I to get an IP from the ISP DHCP server
2. Ping from your router to 8.8.8.8 then to google.com. Do you have a ping reply?
3. Go to your PC and ping to 8.8.8 8. Does it work?
4. From your PC, ping to the router interface 192.168.88.1 - does it work?
5. Check if your PC has a default gateway, if not add it the right default gateway and DNS
6. Ping again from your PC to 8.8.8.8 - does it work?
7. Go the winbox. IP then Firewall and add (NAT).
8. Try now to ping to 8.8 8.8 and google.com from your PC - does it work?

## INTERNET CONNECTIVITY TROUBLESHOOTING

1. Ping from RI to the internet doesn't work but to the upstream (ISP) router works - Solve the issue add new route to route list to next hopping router with 0.0.0.0
2. Rl cannot ping to google.com but can to 8.8.8.8 - Solve the problem. DNS Related. IP > DNS then add manually or IP > DHCP > check peer DNS.
3. The PC can ping to 192.168.88.1 but not further - Solve the problem. can be the gateway or masquerade 
4. The PC can ping to 8.8.8.8 but not to google.com - Solve the  put DNS in ipv4

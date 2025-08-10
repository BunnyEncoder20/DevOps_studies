# IP Addresses in Binary

- We need to know how to convert IP Addresses into Binary form
- As already know each IP address is:
    - 32-bit number
    - each octet is 8 bytes (8 x 4 = 32 bits)
- Eg:
```bash
192.168.1.21
11000000.10101000.00000001.00010101
```
- OR...could just use a calculator to convert IP addresses to binary.

# Subnet Mask

- Subnet mask also presented in binary form
```bash
255.255.255.0
11111111.11111111.11111111.00000000
```
- Remember:
    - 1 = network bits
    - 0 = host bits
- To find the number of hosts can be in the netwrork (through the subnet mask): 2^(number of host bits / or number of 0s) - 2 (for usable IP addrs)
- Eg: in the above subnet mask exaple:
```bash
11111111.11111111.11111111.00000000 = 8 zeros
no. of hosts (ip addresses) = 2^8 - 2 = 256 - 2 = 254 usable ip address.
```
- If we want more ip addresses (say 500), take convert a 1 to a 0:
```bash
11111111.11111111.11111110.00000000 = 9 zeros
no. of hosts (ip addresses) = 2^9 - 2 = 512 - 2 = 510 usable ip address.
```

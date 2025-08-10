# Subnetting and CIDR Notation

- Based on number of subnets required.

## Finding how many bits to flip for no. of subnets
- Remember the following table:
```bash
128 64 32 16 8 4 2 1    # Chart used to convert binary to decimal
256 128 64 32 16 8 4 2  # above chart values x 2
```
- The second one tells us how many host bits we would need to convert (flip to 1) in order to get the number of subnets.
- Eg:
    - if we want to make 4 subnets, we just need the 2 bits.
    - if we want to make 17 subnets, we would need 5 bits (from right till 32 to cover)

## Flip those bits to make subnets
- So if we take our 4 subnet exmaple, and in a network given by:
```bash
192.168.1.0/24
255.255.255.0

# subnet in bin:
11111111.11111111.11111111.00000000
```
- We would need to flip 2 bits to get 4 subnets, which would make it:
```bash
192.168.1.0/26
255.255.255.192

# subnet in bin:
11111111.11111111.11111111.11000000
```
- NOTE: CIDR (/) notation is nothing but the number of **network bits** in the subnet mask (ip_addr/# of network_bits).

## Find the Increment
- it is basically theh number of hosts / ip_addrs in each subnet
- Increment is given by the last network bit decimal value.
- Eg: in our 4 subnet division of:
```bash
192.168.1.0/26
255.255.255.192

# subnet in bin:
11111111.11111111.11111111.192.168.1.0/26
255.255.255.192

# subnet in bin:
11111111.11111111.11111111.11000000
```
- 11000000 last 1 bit is at place of 64. Hence our Increment = 64

## Creating our sub networks

- Cause me now know what our increment is, we can now define the subnet ip addresses ranges:
```bash
192.168.1.0 - 192.168.1.63
192.168.1.64 - 192.168.1.127
192.168.1.128 - 192.168.1.191
192.168.1.192 - 192.168.1.255
```
- Each of the above subnets will have a subnet mask of:
```bash
255.255.255.192 # or
/26
```
- making the network addr of each of the subnets:
```bash
192.168.1.0/26
192.168.1.64/26
192.168.1.128/26
192.168.1.192/26
```

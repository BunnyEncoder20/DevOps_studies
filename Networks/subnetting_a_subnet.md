# Subnetting a Subnet (VLSM)

Question) Company gave a network: 172.21.42.0/24 and we need to cut it up for the factory having 4 networks:
1. guest = 10
2. robots = 57
3. servers = 26
4. workers = 117

---

Answer) Looking at the required subnets, we can see that the total about of hosts required are 210, and we can allocate only about 253 (/24) hosts. So it is possible

## Workers - 117 hosts
- We doing Variable Lenght Subnet Masking (VLSM) you want to start with the largest host requirement first, which in our case is the workers.
- Taking our network addr and subnetting for 117 hosts:
```bash
network = 172.21.42.0
subnet mask = /24 = 255.255.255.0
number of bits whicih will cover 117 hosts = 7 bits
required subnet mask = 11111111.11111111.11111111.10000000 = /25
required subnet mask = 255.255.255.128
increment = 128
subnet range = 172.21.42.0 - 172.21.42.127
```

## Robots - 57 hosts
- Next largest host requirements are for the robots, but instead of taking the base IP addr we were given, we take from the previous subnet
- Hence we will start working on: 172.21.42.128/25
```bash
network = 172.21.42.128
subnet mask = /25 = 1111111.11111111.11111111.10000000
no_of_bits = 6 bits
new_subnet_mask = 111111.11111111.11111111.11000000 = /26
new_subnet_mask = 255.255.255.192
increment = 64
subnet_range: 172.21.42.128 - 172.21.42.191
```

## Servers - 26 hosts
- Next we go the same for the Servers
```bash
network = 172.21.42.191
subnet mask = /26 = 1111111.11111111.11111111.11000000
no_of_bits = 5 bits
new_subnet_mask = 111111.11111111.11111111.11100000 = /27
new_subnet_mask = 255.255.255.224
increment = 32
subnet_range: 172.21.42.192 - 172.21.42.223
```

## Guest - 10 hosts
- same process for guest:
```bash
network = 172.21.42.224
subnet mask = /27 = 1111111.11111111.11111111.11100000
no_of_bits = 4 bits
new_subnet_mask = 111111.11111111.11111111.11110000 = /28
new_subnet_mask = 255.255.255.240
increment = 16
subnet_range: 172.21.42.224 - 172.21.42.239
```

## Conclusion
- The final subnet ranges are:
```bash
172.21.42.0 - 172.21.42.127
172.21.42.128 - 172.21.42.191
172.21.42.192 - 172.21.42.223
172.21.42.224 - 172.21.42.239
```

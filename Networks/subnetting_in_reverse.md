# Subnetting in Reverse

## Getting important info from macbook:
1. IP Address and subnet mask (they were usually under en0 [wifi.ethernet] in macbook):
```bash
ifconfig en0 | grep "inet "
```
2. Default Gateway (not under ifconfig for MacOS)
```bash
route -n get default | grep gateway
```

---

## Finding subnet range from IP and Subnet mask
- cause we already have the subnet mask, we can find the subnetwork mask ranges. 
- Hence we just need to change the subnet mask into binary and find the increment.
- Once we have the increment, we can easily find the ranges
- NOTE: don't invalidate a IP addr just cause it has a 0 or 255 in it's last octet. If the network is big enough, (like a class B network) it can acomodate that and it will be a valid address. 
- Always check if the devices are in the same subnet (range) to be able to conmmunicate with each other.
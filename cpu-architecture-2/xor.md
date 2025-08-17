The following code was based on the design of an XOR gate using only NAND-gates

```
const cp 128
const reg0 0
const reg1 8
const reg2 16
const reg3 24
const reg4 32
const reg5 40
const in 48
const out 6
const bitmask 63
#### end of constants ####
label loop
cp|in|1
cp|in|2
cp|reg1|4
cp|reg2|5
NAND #get A ^ B
# NAND a ^ b with a
cp|reg3|2
cp|reg4|1 
NAND
# store result in reg4
cp|reg3|4
# NAND a^b with b
cp|reg5|1 
NAND
cp|reg3|2
# NAND results of previous 2 ops
cp|reg4|1
NAND
cp|reg3|out
jmp loop
```



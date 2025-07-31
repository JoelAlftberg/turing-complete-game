# Masking Time

Here is the source-code for my solution to the level masking time
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
#### end of constants ####
label loop
cp|in|1
3
cp|reg0|2
### input & 3 == input % 4 ###
and
cp|reg3|out
loop
jmp
```
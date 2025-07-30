# Storage Cracker

Here is the source-code for my solution to the level storage cracker\
Ther are a handful of assembly directories which I have saved such as
- jmp (196) - conditional always
- beq0 (193) - branch when reg3 equal to 0
- add (68) - reg1 + reg 2, store result in reg3
- add (69) - reg1 - reg 2, store result in reg3

```
const reg0 0
const reg3 24
const reg4 32
const in 48
const cp 128
const out 6
##### end of constants #####
# set a starting number
63
cp|reg0|4
# set up our ++/-- number
1
cp|reg0|2
label number_guess
cp|reg4|out
cp|in|3
number_increment
beq0
# decrement
cp|reg4|1
sub
cp|reg3|4
number_guess
jmp
label number_increment
cp|reg4|1
add
cp|reg3|4
number_guess
jmp
```

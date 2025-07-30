# Spacial Invasion

Here is the source-code for my solution to the level spacial invasion

```
const reg0 0
const reg1 8
const reg2 16
const reg3 24
const reg4 32
const reg5 40
const in 48
const cp 128
const out 6
const sub 69
##### end of constants #####
6
cp|reg0|1 #store 6 to r1
1
cp|reg0|2
label forward_six_times
1
cp|reg0|out
sub
cp|reg3|1
forward_six_times
bneq0
0 #turn left
cp|reg0|out
label check_for_enemy
33
cp|in|2
cp|reg0|1
sub
shoot
beq0
3
cp|reg0|out
check_for_enemy
bneq0 
label shoot
5
cp|reg0|out
cp|reg0|out
cp|reg0|out
cp|reg0|out
# check if last turn was left
# if it was go to right turn
# otherwise continue and do left
cp|reg4|reg3
right_turn
bneq0
0
cp|reg0|out
cp|reg0|out
cp|reg0|reg4
check_for_enemy
jmp
label right_turn
2
cp|reg0|out
cp|reg0|out
1
cp|reg0|reg4
check_for_enemy
jmp
```
I'll try to explain briefly what each part of the program does.\
```
6
cp|reg0|1 #store 6 to r1
1
cp|reg0|2
label forward_six_times
1
cp|reg0|out
sub
cp|reg3|1
forward_six_times
bneq0
0 #turn left
cp|reg0|out
```
The purpose of this code is to make a loop that runs 6 times and moves the robot forward for each time the loop runs, after the loop has finished the robot turns left one time so it will face the direction of the invaders.
```
label check_for_enemy
33 
cp|in|2
cp|reg0|1
sub
shoot
beq0
3
cp|reg0|out
check_for_enemy
bneq0 
label shoot
5
cp|reg0|out
cp|reg0|out
cp|reg0|out
cp|reg0|out
```
This portion checks if the robot is inputting the number 33, if it is it jumps to the label **shoot** and shoots 4 times.
If it is not inputting 33, it will output the wait command (3) and then check again.
```
# check if last turn was left
# if it was go to right turn
# otherwise continue and do left
cp|reg4|reg3
right_turn
bneq0
0
cp|reg0|out
cp|reg0|out
cp|reg0|reg4
check_for_enemy
jmp
label right_turn
2
cp|reg0|out
cp|reg0|out
1
cp|reg0|reg4
check_for_enemy
jmp
```
Registry 4  is used to store what direction was turned last time, 0 represents left and any other number than that means right. So at the end of the outputs for the turns a 0 and 1 will be stored in Reg 4 for left and right resopectively. After the robot has turned it will jump back to the **check_for_enemy** loop.  
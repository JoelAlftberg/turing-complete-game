# The-Maze

My source code for The Maze level\
Warning, messy code with lots of comments

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
0
cp|reg0|out

label start
# check if in front of door #
3
cp|reg0|1
cp|in|2
sub
wall_check
bneq0
# open door
4
cp|reg0|out
# check if wall in front #
label wall_check
1
cp|reg0|1
cp|in|2
sub
wall_blocking
beq0
# check wall is not left #
0
cp|reg0|out
1
cp|reg0|2
cp|in|1
sub
empty_f_l 
bneq0 # wall was not left #
### wall was left ###
2
cp|reg0|out
1
cp|reg0|out
start
jmp
### no wall front or left ###
label empty_f_l
# turn 2 right
2
cp|reg0|out
cp|reg0|out
# check right
1
cp|reg0|1
cp|in|2
sub
empty_f_l_r
bneq0 
0
cp|reg0|out
cp|reg0|out
1
cp|reg0|out
start
jmp

#### no wall blocking anywhere ###
label empty_f_l_r
1
cp|reg0|out
start
jmp

label wall_blocking
### check if wall in front ###
#turn left
0
cp|reg0|out
### check in front
1
cp|reg0|2
cp|in|1
sub
blocking_f_l
beq0
1
cp|reg0|out
start
jmp
### checking right after f_l blocke
label blocking_f_l
2
cp|reg0|out
cp|reg0|out
1
cp|reg0|1
cp|in|2
sub

blocking_f_l_r
beq0
1
cp|reg0|out
start
jmp

### walls blocking all directions###
label blocking_f_l_r
0
cp|reg0|out
cp|reg0|out
start
jmp
```
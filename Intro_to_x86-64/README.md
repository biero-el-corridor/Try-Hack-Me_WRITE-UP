|name     | difficulty | room author | Walkthrougt autor |
|---------|------------|-------------|-------------------|
|Sample   |  easy      | Try hack me | biero el corridor |



Task 1 Description and Objectives \
Task 2 Introduction \
Task 3 If Statements \
Task 4 If Statements Continued \
Task 5 Loops \
Task 6 crackme1 \
Task 7 crackme2 



## Task 1 : Description and Objectives 

KEY INFO 
+ Whe will use the AT&T synatax 
+ Username and password fot the room is tryhackme/reismyfavl33t (ssh). 

## TASK 2 : Introduction 

KEY INFO 
+ code is translated to computer code when compiled. 
+ the computer can build 8 , 16, 32 and 64 bit sized instructions
+ we’ll be looking at the Intel x86-64 instruction

COMMAND 

    r2 -d intro
    ///////////////////////////////////
    r2 = command for laught radar2
    -d = debug mode
    intro = file name
    ///////////////////////////////////

    aa
    ///////
    analyse all symbols and entry points in the executable.
    ///////

    afl
    ///////
    show all funtions present in the executable
    ///////

    pdf @Funt_Name
    ///////
    pdf stand for Print Disassembly Function
    ///////

INSTRUCTIONS EXPLAINED 

    addq source, destination
    ////
    destinations = destinations + source
    ////

    subq source, destination
    ////
    destination = destination - source
    ////

    imulq source, destination
    ////
    destination = destination * source
    ////

    salq source, destination
    bit shifted 
    ///////////////////////////////////////////////
    ex: sal
    hex preresentations of sal $1, 0x16 ()
    <<--------------------------------------
|0 | 8 | 4 | 2 | 1 | XX | 8 | 4 | 2 | 1 | 
|--|---|---|---|---|----|---|---|---|---|
|1 | 0 | 0 | 0 | 1 | XX | 0 | 1 | 1 | 0 |
|2 | 0 | 0 | 1 | 0 | XX | 1 | 1 | 0 | 0 |
|3 | 0 | 1 | 0 | 1 | XX | 1 | 0 | 0 | 0 |
|4 | 1 | 0 | 1 | 1 | XX | 0 | 0 | 0 | 0 |

    as you see the bit have shifted to 1 in the left
    so after 4 sal 0x16 have become 0xB0
    ///////////////////////////////////////////////

    sar source, destination
    ///////////////////////////////////////////////
    ex: sar 
    hex preresentations of sar $1, 0x16 ()
    <<--------------------------------------
|0 | 8 | 4 | 2 | 1 | XX | 8 | 4 | 2 | 1 |
|--|---|---|---|---|----|---|---|---|---| 
|1 | 0 | 0 | 0 | 1 | XX | 0 | 1 | 1 | 0 |
|2 | 0 | 0 | 0 | 0 | XX | 1 | 0 | 1 | 1 |
|3 | 0 | 0 | 0 | 0 | XX | 0 | 1 | 0 | 1 |
|4 | 0 | 0 | 0 | 0 | XX | 0 | 0 | 1 | 0 |

    as you see the bit have shifted to 1 in the Right
    so after 4 sal 0x16 have become 0x02

    xorq source, destination 
    ////
    destination = destination XOR source
    [XOR Gate wikipedia page](https://en.wikipedia.org/wiki/XOR_gate)
    ////

    andq source, destination: 
    ////
    destination = destination & source
    [AND Gate Wikipedia page](https://en.wikipedia.org/wiki/AND_gate)
    ////

    andq source, destination: 
    ////
    destination = destination & source
    [OR Gate wikipedia](https://en.wikipedia.org/wiki/OR_gate)
    ////

## Task 3 If Statements 

KEY INFO 

+ there is assembly fontions for use if (cmp and test)
+ there is jump instructions with specificity for go to specific memory space

## Task 4 If Statements Continued 

KEY INFO 

+ db is use for make a breakoint to a specific memory area, this is relly usefull for see the advence of the value
+ dr is use for view the hex value of the different 64 bit register
+ px @var_name allow to see the content of the var_name
+ ds allow to go to the nex breakpoint of end of the program if theyr are no breakpoint. 

QUESTIONS

1 as we see var_8h is present 2 time \

    when var_8h get the vlalue 0x63
    movl $0x63, var_8h

    and when var_8h have a and operator use with 0x64
    movl $0x64, var_8h

hex  | 8 | 4 | 2 | 1 | XX | 8 | 4 | 2 | 1 |
|----|---|---|---|---|----|---|---|---|---|
0x63 | 0 | 1 | 1 | 0 | XX | 0 | 1 | 0 | 0 |
0X64 | 0 | 1 | 1 | 0 | XX | 0 | 0 | 1 | 1 |
and  | 0 | 1 | 1 | 0 | XX | 0 | 0 | 0 | 0 |

    for the purpose of the walkthrougt i dont translta to decimal value. 

2 what is the value of var_ch before the popq and ret instructions? 

    watch closely and you see that the value dont chage

3 What is the value of var_4h before the popq and ret instructions? 

    watch closely and you see that a substitutions funtions ocure a the end between 2 hex value

4 What operator is used to change the value of var_8h, input the symbol as your answer(symbols include +, -, *, /, &, |): 

    I recomend you to go to the wikipedia page of the AND logical gate


## Task 5 Loops 

KEY INFO

+ Two type of loop are used (for and while)
+ make a db in each of the jump sections for see the advencement of the program

QUESTIONS

1 What is the value of var_8h on the second iteration of the loop?

    see the exemple in the introdutions

2 What is the value of var_ch on the second iteration of the loop?

    We can see that a and operator is use check the wikipedia page of the AND logical gate. 

3 What is the value of var_8h at the end of the program?

    see the exemple in the introdutions

4 What is the value of var_ch at the end of the program?

    We can see that a and operator is use check the wikipedia page of the AND logical gate. 

## sTask 6 crackme1 

for this one whe will use the v funtions in radare2, this funtions show the hex and string value of the file. \

after made this command

    r2 -d crackme1
    aaa
    v @main 

we can see the moment where the sting is present\
and a other interesting thing , is the presence of XXX.X.X.X after the "enter the password"

<p align="center">
    <img src="https://github.com/biero-el-corridor/Try-Hack-Me_WRITE-UP/blob/main/Intro_to_x86-64/picture/crackme1-string.png"/>
</p>


After this report we search in the main funtion , and see that a . delimiter is set and the begening in 127

<p align="center">
    <img src="https://github.com/biero-el-corridor/Try-Hack-Me_WRITE-UP/blob/main/Intro_to_x86-64/picture/crackme1-dot.png"/>
</p>


## sTask 7 crackme2

The same as the crackme1 , we see the sting with the visual mode\

This time this is not a string but a path that we see. 

<p align="center">
    <img src="https://github.com/biero-el-corridor/Try-Hack-Me_WRITE-UP/blob/main/Intro_to_x86-64/picture/crackme2-filepath.png"/>
</p>

We confirm that a file is read by the presence of the fontions fread and fopen in the funtions list.

<p align="center">
    <img src="https://github.com/biero-el-corridor/Try-Hack-Me_WRITE-UP/blob/main/Intro_to_x86-64/picture/crackme2-fontions.png"/>
</p>

but the paswword dont work\

after searching a bit we see a reversing dtring fontions inthe assembly; 

<p align="center">
    <img src="https://github.com/biero-el-corridor/Try-Hack-Me_WRITE-UP/blob/main/Intro_to_x86-64/picture/crackme2-reverse.png"/>
</p>

so we reverse the string and that work. 

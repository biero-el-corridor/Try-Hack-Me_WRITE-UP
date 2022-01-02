|name          | difficulty | room author | Walkthrougt autor |Category|
|--------------|------------|-------------|-------------------|--------|
|Classic Passwd| Medium     | N0obit4     | biero el corridor |Reverse |

Task 1 Get the flag 


## Task 1 Get the flag 

For this challenge we have a file to download. 

We know that is a reverse challenge so, we first need to know what file type this file is 

<p align="center">
    <img src="https://github.com/biero-el-corridor/Try-Hack-Me_WRITE-UP/blob/main/sample/THM_logo.png"/>
</p>

after that we run radare 2 to see what it's inside this binary

The main funtion
<p align="center">
    <img src="https://github.com/biero-el-corridor/Try-Hack-Me_WRITE-UP/blob/main/sample/THM_logo.png"/>
</p>

We can see 2 funtions call 
    sym.vuln
    sym.gfl

We can assume that the name vulm is suspicious , so we go in there. \

In this funtions we can see one thing interesting 
    if the strcmp is not succeful the bin is closed
    The test value before the JNE and the JNE

<p align="center">
    <img src="https://github.com/biero-el-corridor/Try-Hack-Me_WRITE-UP/blob/main/sample/THM_logo.png"/>
</p>

In the challenge intro the creator speak about bypassing password.\

And after analyse the second funtions we can see that if the flag is correct in vuln so the flag is given in gfl.\

<p align="center">
    <img src="https://github.com/biero-el-corridor/Try-Hack-Me_WRITE-UP/blob/main/sample/THM_logo.png"/>
</p>

After a bit of research i found the awnser in a stack overflow tread\
https://stackoverflow.com/questions/14267081/difference-between-je-jne-and-jz-jnz

so we can modifi the 75 value that define JNE to 74 , 74 is the hex value to define JE. 

This actions will cause the reverse of the if. 

I use hexeditor to find and modify the 75 value in the hex

<p align="center">
    <img src="https://github.com/biero-el-corridor/Try-Hack-Me_WRITE-UP/blob/main/sample/THM_logo.png"/>
</p>

After modifi 75 to 74 we run the bin and tada the flag popup.

<p align="center">
    <img src="https://github.com/biero-el-corridor/Try-Hack-Me_WRITE-UP/blob/main/sample/THM_logo.png"/>
</p>
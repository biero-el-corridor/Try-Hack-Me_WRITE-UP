|name     | difficulty | room author | Walkthrougt autor |
|---------|------------|-------------|-------------------|
|Sample   |  easy      | Try hack me | biero el corridor |



Task 1 Description and Objectives 
Task 2 Introduction 
Task 3 If Statements
Task 4 If Statements Continued 
Task 5 Loops 
Task 6 crackme1 
Task 7 crackme2 



Task 1 : Description and Objectives 

KEY INFO 
    + Whe will use the AT&T synatax 
    + Username and password fot the room is tryhackme/reismyfavl33t (ssh). 

TASK 2 : Introduction 

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

    imulq source, destination: destination = destination * source

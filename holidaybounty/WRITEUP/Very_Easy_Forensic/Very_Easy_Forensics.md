## Very Easy Forensics - TBF1 HOLIDAY BOUNTY 2025

![ChallImage](attachments/image.png)

- **Category:** Forensic
- **Challenge Author:** LTFZP
- **Solver:** Mekakushi Dan Member No.0
- **Date:** 05/01/2026
- **Point:** 500

## Intro
In this challenge I was given png file that named "easy4n6.png", if we look at that file we can only see something like broken image. Like another forensic challenge I try to use some of command that might help me to unveil the clue and maybe the flag :).

## Digging Time?
I start by using some basic command like strings, file, head, etc but I couldn't find any clue. Then I start to digging up some information, and i found tools in Github that called zsteg, with this tools we can detect stegano-hidden data in PNG & BMP

## Solving Time?
We begin the procces with
>zsteg -a easy4n6.png

that command give us some valuable information, and one of the line stood out, thats `b8,rgba,lsb,xy      .. text: "Congrats.png"`, with this line we can know that there is `Congrats.Png` file inside the easy4n6.png. The next step is Extracting the `Congrats.Png` file with command `zsteg -E b8,rgba,lsb,xy easy4n6.png > Congrats.png`

Hmmm.... is this the end??, unfortunately no. When I try to open the `Congrats.png` something that I meet is this 

![alt text](attachments/image-1.png)

We need to dig more information from this file and after I try to binwalk the file we have some precious information, Basically the png is start from offset 286.

 another information that strengthen this finding is that if we try to see the header of the file with `xxd` command, we can see bunch junk data until offset 286, even though a png should start with  `89 50 4e 47` which are missing in this file. Soooooo what is the solution of this problem???, the easiest solution is to use ` binwalk -e Congrats.png`, with this command we can automatically carve and extract the real png that contain the flag.

## FLAG

![alt text](attachments/image-2.png)

>TBF1{7hi5_i5_7HE_e@sieS7_ForEn51C_CH4L1_IvE_evER_MaD3}

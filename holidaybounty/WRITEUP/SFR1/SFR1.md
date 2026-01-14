## SFR 1 - TBF1 HOLIDAY BOUNTY 2025

![alt text](attachments/image.png)

- **Category:** Beginner
- **Challenge Author:** Ireng_Sigma
- **Solver:** Mekakushi Dan Member No.0
- **Date:** 05/01/2026
- **Points:** 388

## Intro
![alt text](attachments/broke.jpg)

SFR1 is a beginner problem that provides the file `broke.jpg` for us to analyze. It looks quite intimidating, but is this problem as difficult as I imagine? Let's try to solve it.


## Solving Time ..
When I try to solve challenge that involve imagea, I like to try some basic command, another reason of my action is that this challenge is a part of beginner category. after some basic command like `file`, `binwalk`, `exiftool`, etc, I didnt find the clue. Initial analysis using binwalk revealed no embedded files. Further inspection of metadata using exiftool showed a suspicious title 'yeah, it's nothing - 1' and indications that the image was exported from Canva, but no flag was found in the metadata tags. and then i try 
` strings -n 4 broke.jpg | grep TBF`
fortunately this simple approach gives me the flag and the flag is............
>FLAG: TBF1{r3scu1ng_9oph3r5_fr0m_flo0d5}

We Succesfully Rescueing Gopher from the flood
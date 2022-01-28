# Lab Report Week 4
## Andrew Dai A16366706
---
---
## Code Change 1
**Bug fix 1:**
![bugfix1](bugfix1.png)
Link to test file:
[link to test file](https://github.com/andrewdai1/cse15l-lab-reports/blob/main/test-file2.md)

**Error message:**
![bug1](bug1.png)

**Explanation:**
The bug was due to the program assuming that everything is a 
link: when it encountered a markdown file with extra text 
("hello!" in this case), it kept on looping forever trying to 
find the next open bracket.
This caused Java to go into an infinte loop and run out of 
memory, resulting in an error message.


## Code Change 2
**Bug fix 2:**
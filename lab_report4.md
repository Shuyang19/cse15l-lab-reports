# Lab Report 4
## Part 1

The shortest sequence to change the name of the start parameter and its uses to base:
```
/
start
<enter>
ce
base
<esc>
n
.
n
.
n
.
n
:wq
<enter>
```
- the `/star` command will find the string after it (in my command is start), then press `<enter>`, the cursor will move to the front of the string "start"
![Image](4.1.jpg)
- the `ce` command will delete the word start and let you into the INSERT MODE
![Image](4.2.jpg)
- then enter `base`
![Image](4.3.jpg)
- press`<esc>` to escape the insert mode and back to normal mode
- the command `n` will find the next start in the file
![Image](4.4.jpg)
- press `.` to repeat last command, which is deleting start and insert base
![Image](4.5.jpg)
- repeat the command `n` and `.` until get the notice that there aren't any start in the file
![Image](4.6.jpg)
- the command `:wq` will save the file and exit vim


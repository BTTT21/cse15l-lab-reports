# Lab Report 4
**Log into ieng6:**

<img width="814" alt="Screenshot 2023-11-14 at 11 37 44 AM" src="https://github.com/BTTT21/cse15l-lab-reports/assets/146874113/58a80ba9-d812-4b57-b50f-e89be9bfb1f0">

>Keys pressed: ssh cs15lfa23kt@ieng6.ucsd.edu\<enter\>  
>Commands summary: I used command ssh to log into ieng6 and pressed \<enter\> to run the command.

**Clone your fork of the repository from your Github account (using the SSH URL):**

<img width="725" alt="Screenshot 2023-11-14 at 11 38 22 AM" src="https://github.com/BTTT21/cse15l-lab-reports/assets/146874113/09ef8fe2-52e0-4bb4-846f-bfb72540a054">

>Keys pressed: git clone git@github.com:BTTT21/lab7.git\<enter\>  
>Commands summary: I used the clone option of the command git to clone my fork of the repository and pressed \<enter\> to run the command.

**Run the tests, demonstrating that they fail:**

<img width="597" alt="Screenshot 2023-11-14 at 11 39 01 AM" src="https://github.com/BTTT21/cse15l-lab-reports/assets/146874113/943b898e-638d-4403-8505-8706d4c31e13">

>Keys pressed: ls\<enter\>cd lab7\<enter\>ls\<enter\>bash tes\<tab\>\<enter\>  
>Command summary: I first used command ls to see what was inside the current directory. Then I used command cd to go into the folder "lab7" I cloned. Next, I used command ls to see what was inside the "lab7" folder. I saw the "test.sh" was here so I type "bash tes". I knew that was the only file that started with "tes", so I used \<tab\> to come up with the full name and ran the command bash test.sh to run the test.

**Edit the code file to fix the failing test:**

<img width="410" alt="Screenshot 2023-11-14 at 11 46 44 AM" src="https://github.com/BTTT21/cse15l-lab-reports/assets/146874113/fce3064d-dbfc-489a-91bc-fd0c7438721c">

>Keys pressed: vim Lis\<tab\>\<enter\>  
>Command summary: I used command vim to go into vim mode to edit the java file. I knew there was two files started with "Lis", but since I want "ListExamples.java", the one with a shorter name, I used \<tab\> to come up with the full name and pressed \<enter\> to run the command.

<img width="617" alt="Screenshot 2023-11-14 at 11 40 37 AM" src="https://github.com/BTTT21/cse15l-lab-reports/assets/146874113/9cf72609-4459-4b21-a029-447cfa91f4b5">

>Keys pressed: \<shift g\>kkkkkkeli\<delete\>2\<esc\>\<shift ;\>wq\<enter\>
>Command summary: I pressed command \<shift\> and g together to move to the end of the code. Then I pressed k for six times to move up to the correct line I was going to edit. Next, I pressed e to move to the end of the first word, which was "index1". My cursor was at "1" of "index1", so I pressed l to move one index further. I pressed i to go to insert mode and pressed \<delete\> to delete "1" from "index1". After that I pressed 2 to add "2" and pressed \<esc\> to exit insert mode. Since I finished my edit, so I pressed \<shit\> and ; together, and then pressed wq \<enter\> to save and quit the vim mode.

**Run the tests, demonstrating that they now succeed:**

<img width="362" alt="Screenshot 2023-11-14 at 11 47 32 AM" src="https://github.com/BTTT21/cse15l-lab-reports/assets/146874113/5e01dadd-7c9c-489c-af29-04a1936bada8">

>Key pressed: \<up\>\<up\>\<enter\>  
>Command summary: since the command "bash test.sh" was in my command history, the command line before the previous command, I used command \<up\> twice to use it again and pressed \<enter\> to run the command.

**Commit and push the resulting change to your Github account (you can pick any commit message!):**

<img width="510" alt="Screenshot 2023-11-14 at 11 48 30 AM" src="https://github.com/BTTT21/cse15l-lab-reports/assets/146874113/f512f5f6-8211-4b99-b401-1330a0c0fb41">

>Key pressed: git add Lis\<tab\>\<enter\>git commit -m "update"\<enter\>git push\<enter\>  
>Command summary: I used the command git add to add the file I want to push, which was "ListExamples.java". I typed the name of the java file using the same method before, which was Lis then \<tab\>. I pressed \<enter\> to run the command. Then I used command git commit to put what I want to commit. I put "update" for the commit with quotation marks and pressed \<enter\> to run the command. Finally, I used the command git push to push my changes.


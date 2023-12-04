# Lab Report 4
## Step 4: Log into ieng6
<img width="647" alt="Screenshot 2023-12-01 at 11 19 59 AM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/3368be73-da3a-4d8c-b2c6-3aa2a3070797">

The keys pressed: `ssh<space>cs15lfa23mt@ieng6.ucsd.edu<enter>`
I input the command `ssh` and my ieng6 account `cs15lfa23mt@ieng6.ucsd.edu` and hit `enter` button to log in to my ieng6 account.

## Step 5:Clone your fork of the repository from my Github account (using the SSH URL)
<img width="823" alt="Screenshot 2023-12-03 at 6 37 13 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/6967b351-907a-47d3-97bd-33cf041c4a21">

The keys pressed: `git clone<space><ctrl+v><enter>`
I copy the SSH URL link from my Github page and in the terminal, I input the command `git clone` and use shortcut `<ctrl+v>`to paste the SSH URL link and hit `enter` button to clone my fork of the repository.

## Step 6:Run the tests, demonstrating that they fail
<img width="736" alt="Screenshot 2023-12-03 at 6 40 04 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/d0dced6c-99cc-450f-85b6-c4cde8a4009a">
The keys pressed: `cd<space>lab7<enter>bash test.sh<enter>`
I use the `cd` command to change my working directory to `lab7` and then use the `bash` command to run the `test.sh`.

## Step 7:Edit the code file to fix the failing test
<img width="682" alt="Screenshot 2023-12-03 at 6 53 08 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/c0319166-1c90-4fc6-abf1-73bb9c17cd15">

The key pressed: vim<space>ListExamples.java<enter>44<shift+g>er2:wq!<enter>
I use `vim` command to access the `ListExamples.java` file. According to the test fail message from step 6, I know that the error occur in line 44. Therefore, I used `44<shift+g>` to shift to line 44 and the `i` of `index1` is highlighed. I type in `e` to shift to the last letter of this current word `2` and use `r` to replace the current letter to `2`. After finish editing the file, I use ":wq!" to save the changes and exit the file. 

## Step 8:Run the tests, demonstrating that they now succeed
<img width="472" alt="Screenshot 2023-12-03 at 8 22 14 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/4cd7a2f3-0b11-4057-915f-e1fc3db21d0b">
The keys pressed: `<up><up><enter>`
The same test running command is used in step 6, therefore I used the <up> key twice to find the history and run it.
  
## Step 9:Commit and push the resulting change to your Github account (you can pick any commit message!)
<img width="764" alt="Screenshot 2023-12-03 at 8 43 18 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/58b919a8-60f7-4783-b56b-333b15a5d370">
The key pressed: `git<space>add<space>ListExamples.java<enter>git<space>command<space>-m<space><shift+'>Fixed<space>ListExamples.java<enter>git<space>push<enter>`
I use `git add` command to `ListExamples.java` file and use the 'git commit` and `-m` to add the commit message `"Fixed ListExamples.java"` to the java file. In the end, I use `git push` command to push the changes to Github.

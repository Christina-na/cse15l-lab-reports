# Lab Report 5
## Part 1 – Debugging Scenario

### Original post from a student

Hi there,
I'm having an issue with my `grade.sh` script. I'm trying to clone a student's repository and set up some directories, but it seems like something is not working. Here's a screenshot of the error I'm getting:

<img width="947" alt="Screenshot 2023-12-03 at 10 32 06 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/6750a0cc-d035-41ba-9fa6-e8dd75eaea8d">

Here's a screenshot of my `grade.sh` script:
<img width="890" alt="Screenshot 2023-12-03 at 10 45 01 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/cd700830-7576-412c-8c86-939374db9b49">

I think the issue might be related to the cloning part, but I'm not sure. In my grade.sh file, I defined `student-submission` and used `git clone` command to clone the submission. Any help or guidance would be appreciated!


### TA's Response
Hi there! Thank you for reaching out. It looks like the issue might be related to the git clone command in your grade.sh script. The error message suggests that the repository URL might not be passed correctly or that there's an issue with the cloning process. In this case, the git clone command does not having the correct parameters. 


### Student's Reply

Thanks for your reply! I realize that here was no positional parameter in my original code that that represents the first command-line argument passed to the script. The line  `git clone student-submission` is equivalent to `git clone`, and Git expects a repository URL to be provided after the git clone command. Since there's no repository URL specified, Git interprets "student-submission" as the repository name, but it doesn't exist, resulting in an error. I need to include a "$1" after my "git clone" command to refer to pass the first command-line argument to the script.

Here's the updated code:
<img width="750" alt="Screenshot 2023-12-03 at 10 50 58 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/893fd209-e22f-45be-a00e-e8e84a28894b">

Here's the succesful running result:
<img width="871" alt="Screenshot 2023-12-03 at 10 53 26 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/9b548eb1-1cd4-4655-893e-4ba93556a1be">

### Additional Information

#### File Structure

The file structure is the same as week 6's [list-examples-grader](https://github.com/ucsd-cse15l-s23/list-examples-grader)

####

6##Part 2 – Reflection

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

#### File & Directory structure

The File & Directory structure is the same as week 6's [list-examples-grader](https://github.com/ucsd-cse15l-s23/list-examples-grader). 

#### File Content - grade.sh (orignal)

```
CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'

rm -rf c
rm -rf grading-area

mkdir grading-area

git clone $1 student-submission
echo 'Finished cloning'


# Draw a picture/take notes on the directory structure that's set up after
# getting to this point

# Then, add here code to compile and run, and do any post-processing of the
# tests

```

#### File Content - ListExamples.java
```
import java.util.ArrayList;
import java.util.List;

interface StringChecker { boolean checkString(String s); }

class ListExamples {

  // Returns a new list that has all the elements of the input list for which
  // the StringChecker returns true, and not the elements that return false, in
  // the same order they appeared in the input list;
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(s);
      }
    }
    return result;
  }


  // Takes two sorted list of strings (so "a" appears before "b" and so on),
  // and return a new list that has all the strings in both list in sorted order.
  static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index2 += 1;
    }
    return result;
  }


}
```

#### Full command line you ran to trigger the bug
`bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected`

### Description of what to edit to fix the bug
In the original code, the line git clone student-submission attempts to clone a repository without specifying a repository URL. This is because there is no positional parameter `$1` to capture the first command-line argument provided to the script. As a result, Git interprets `student-submission` as the repository name, leading to an error because the repository doesn't exist.To resolve this issue, I included `$1` after the `git clone` command. The addition of `$1` allows the script to capture the first command-line argument, which should be the repository URL.

##Part 2 – Reflection
In the second half of this quarter, I learned the power and efficiency of using Vim as a text editor. I discovered various commands, shortcuts, and plugins that significantly improved my coding workflow. Vim's modal interface and extensibility have made it a versatile tool. I also learn the advantage of SSH URLs, which provide a secure way to authenticate and interact with remote repositories without needing to enter a username and password for every interaction.

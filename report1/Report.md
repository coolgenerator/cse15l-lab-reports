# Lab Report 1 - Remote Access and FileSystem (Week 1)

## Requirements
For each of the commands `cd`, `ls`, and `cat`, and using the workspace you created in this lab:
+ Share an example of using the command with no arguments.
+ Share an exmaple of using the command with a path to a directory as an argument.
+ Share an example of using the command with a path to a file as an argument. \

For each, include:
+ A screenshot or Markdown code block showing the command and its output
+ What the working directory was when the command was run
+ A sentence or two explaining why you got that output (e.g. what was in the filesystem, what it meant to have no arguments).
+ Indicate whether the output is an error or not, and if it’s an error, explain why it’s an error.

## Results
![Image](filesystem.png)

### For commands with no arguments
My initial working directory was `/home/lecture1`

When I used `cd` commend with no arguments, the working directory changed to the home directory. There is no output by executing this command.

After executing the above command, my working directory changed to `/home`

When I used `ls` commend with no arguments, the output displayed all the files under `/home` directory. In my case, there is a file in blue, so I know there is a **lecture** directory under my home directory.

After executing the above command, my working directory is still `/home`

When I used `cat` commend with no arguments, it started with a new line. There is no output in this case. I googled it, it says it will wait for your input from the keyboard until it receives an end-of-file signal. So I tried it one more time, it repeated what I typed in in a new line when I end with a return button, and repeated my input in the same line once after I type 'Ctrl + D'

![cat](cat_command.png)

### For commands with a path to a directory as an argument
My initial working directory was `/home`

When I used `cd` commend followed with the `lecture1` directory, the working directory changed to `/home/lecture1`. There is no output by executing this command.

After executing the above command, my working directory changed to `/home/lecture1`

When I used `ls` commend followed with the `lecture1` directory, the output displayed all the files under `/home/lecture1` directory. There are four files under the `lecture1` directory.

After executing the above command, my working directory is still `/home/lecture1`

When I used `cat` commend followed with the `lecture1` directory, it displayed 'cat: messages/: Is a directory'. This is an error that the `cat` command should not followed by a directory path.


### For commands with a path to a file as an argument
My initial working directory was `/home/lecture1`

When I used `cd` commend followed with the `Hello.java` file, it displayed 'bash: cd: Hello.java: Not a directory'. This is an error that the `cat` command should not followed by a file path.

After executing the above command, my working directory remains `/home/lecture1`

When I used `ls` commend followed with the `Hello.java` file, the output displayed the file name 'Hello.java'.

After executing the above command, my working directory remains `/home/lecture1`

When I used `cat` commend followed with the `Hello.java` file, it displayed all the file content in 'Hello.java' file. There was no error displayed.


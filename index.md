# Welcome to YourMorning

YourMoring is a setup guide intended for Mac users. In this guide, you'll learn how to 
create a bash command that opens daily webpages accessed (typically) in the morning.

## Background

This guide assumes you have access to a computer and preferably some programming experience. This guide uses Python, but is easily adaptable to another language; use whatever is comfortable.
Some experience in bash scripting is also helpful, but not required.

## Enumerating Your Needs
1. Computer
2. [Python Interpreter](https://www.python.org/downloads/)
3. [Text Editor](https://code.visualstudio.com/)
4. Access to Terminal

### Note: 
If you need more help with the above list, search stackoverflow
for better, more explicit explanations than provided here.

## Let's Get Started

### Creating the Project Folder
Create a project folder titled 'MyMorning' either in your Desktop folder (your home screen)
or another project folder.<br />
Note:<br />For instruction's sake, I'll assume that the folder is located on the home screen.<br />

Now that you have a home for your project, let's open the Terminal and navigate to this folder.<br />
Open Terminal and type the command:<br />
```markdown
cd ~/Desktop/MyMorning
```
### Writing the Python Script
Using either a text editor, the folder explorer on your OS, or the terminal, create and open a file 
named "mymorning.py". The guide creates the file in the terminal and opens the file in VSCode.<br />
Use the following command:<br />
```markdown
touch ./mymorning.py
code ./mymorning.py
```
Notes:<br />'touch' is a bash command to create a file. <br />
'code' is another command used here to open our target file.
<br /><br />
Add the following code to this file:
```markdown
import webbrowser

#function for opening websites in a browser
def open_daily(websites):
        for website in websites:
                webbrowser.open(website)

#variables to hold website urls; customize as you wish
google = "https://www.google.com/"
github = "https://github.com/acdlee" 
music = "https://www.youtube.com/watch?v=5qap5aO4i9A"

#websites is a list of websites you wish to open when running the script
websites = [google, github, music]

open_daily(websites)
```

Then, save the file with the following command:<br />
```markdown
CTRL-S
```
      
### Running the Python Script
To ensure everything's working, type the follow command:<br />
```markdown
python3 mymorning.py
```
You should open 3 webpages: Google, my Github, and some lofi music.<br />
If you run into some issues, feel free to access the Oracle that is Google. 

### Writing the bash command
We will now navigate to our .bash_profile and write a new command.
On Mac or Linux, you can simply type "cd" to navigate to your .bash_profile.
On Windows, I recommend reopening the terminal.
Follow the following commands to open your .bash_profile : <br />
```markdown
code .bash_profile
```
Enter the following text in this file and save the file with
the previous emacs commands mentioned above:
```markdown
alias morning='python ~/Desktop/FILEPATH/MyMorning/mymorning.py'
```
where FILEPATH is the location of your MyMorning folder. <br />
Finally, enter the command:<br />
```markdown
source .bash_profile
```
Here, you're aliasing the command "morning" with the command line input
of<br /> 'python ~/Desktop/FILEPATH/MyMorning/mymorning.py'.<br /> Said another way, 
when you type 'morning' in terminal, you'll run the python file
'mymorning.py'. <br />
Note:<br />
'source .bash_profile' is just a command "updating" your .bash_profile.
Any change to this file must be followed by this command for it to work. 

### Try It Out!
Enter the following command to verify the script works correctly:
```markdown
morning
```
You should have the three aformentioned webpages (or any others you may have
added) open up. 

## Wrap Up
That's all there is to it! Experimenting with your .bash_profile is a fun
and easy way to be creative with your terminal window. Some other quick examples 
of what you can do:<br />
-change the colors of your directories in the terminal<br />
-alias directories for quick access<br />
-open jupyter notebook in a specific directory with a one-word command<br />
-alias compilers and interpreters<br /> 

**Thanks** for reading! I hope this guide was helpful and informative. Reach out through Github
with any questions or recommendations for this quick guide.

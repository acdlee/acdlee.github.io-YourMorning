# Welcome to YourMorning

YourMoring is a setup guide intended for Mac users. In this guide, you'll learn how to 
create a bash command that opens daily webpages accessed (typically) in the morning.

## Background

This guide assumes you have access to a Mac and at least some prior programming
knowledge. The choice of the programming language is yours alone, however, I 
encourage Python; justified primarily by its ease and swiftness (earnestly, no pun intended). 

## Enumerating Your Needs
1. Mac
2. [Python Interpreter](https://www.python.org/downloads/mac-osx/)
3. [Emacs](https://www.gnu.org/software/emacs/download.html)
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
Using either Emacs, your favorite IDE, or your favorite text editor, create and open a file 
named "mymorning.py". I'll assume you're opting for emacs.<br />
Use the following command:<br />
```markdown
emacs -nw mymorning.py
```
Notes:<br />'emacs' is a command to open the command line text editor, Emacs <br />
       '-nw' is a command line argument selecting the "no window" option for the emacs text editor
<br /><br />
Add the following code to this file:
```markdown
import webbrowser

#function for opening websites in a browser
def open_daily(websites):
        for website in websites:
                webbrowser.open(website)


#websites is a list of websites you wish to open when running the script
websites = ["https://www.google.com/", 
           "https://github.com/acdlee", 
           "https://www.youtube.com/watch?v=5qap5aO4i9A"]
open_daily(websites)
```

Then, save the file with the following command:<br />
```markdown
CRTL-X CTRL-S
```
And exit the file:<br />
```markdown
CTRL-X CTRL-C
```
Note:<br />"CRTL-X CTRL-S" means you hold down the CTRL key and press the X key,
      and then hold down the CTRL key and press the S key.
      
### Running the Python Script
To esnure everything's working, type the follow command:<br />
```markdown
python3 mymorning.py
```
You should open 3 webpages: Google, my Github, and some lofi music.<br />
If you run into some issues, feel to access the Oracle that is Google. 

### Writing the bash command
We will now navigate to our .bash_profile and write a new command.
Follow the following commands to open your .bash_profile : <br />
```markdown
cd
emacs -nw .bash_profile
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
That's all there is to it! Experimenting with you .bash_profile is a fun
and easy way to be creative with your terminal window. Some other quick examples 
of what you can do:<br />
-change the colors of your folders in the terminal<br />
-alias directories for quick access<br />
-open jupyter notebook in a specific directory with a one-word command<br />
-alias compilers and interpreters<br /> 

**Thanks** for reading! I hope this guide was helpful and informative. Reach out with Github
with any questions and I'll be happy to help.

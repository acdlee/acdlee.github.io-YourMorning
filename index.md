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
**emacs -nw mymorning.py**<br />
Notes:<br />'emacs' is a command to open the command line text editor, Emacs; <br />
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
**CRTL-X CTRL-S**<br />
And exit the file:<br />
**CTRL-X CTRL-C**<br />
Note:<br />"CRTL-X CTRL-S" means you hold down the CTRL key and press the X key,
      and then hold down the CTRL key and press the S key.
      
### Running the Python Script
To esnure everything's working, type the follow command:<br />
**python3 mymorning.py**<br />
You should open 3 webpages: Google, my Github, and some lofi music.<br />
If you run into some issues, feel to access the Oracle that is Google. 

### Writing the bash command
We will now navigate to our .bash_profile and write a new command.
Follow the following commands to open your .bash_profile : <br />
**cd** <br />
**emacs -nw .bash_profile** <br />

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/acdlee/acdlee.github.io-YourMorning/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.

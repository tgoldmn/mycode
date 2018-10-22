# mycode
tgoldmn@optonline.net github email address tgoldmn 
# mycode (Project Title)

One Paragraph of your project description goes here. Describe what you're trying to do. What is the purpose of putting up this repo?

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

What things you need to install the software and how to install them. For now, maybe copy in how to install python and python3 using apt.

```
Give examples
```

### Installing

A step by step series of examples that tell you have to get a development env running. Eventually, maybe we could list Python package requirements here. You can remove this section for now, or make a note to yourself to fill it out later.

```
Give the example
```

And repeat other install steps...

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo


    ## Running the tests

    Explain how to run the automated tests for this system. We don't have any, so just make a note that they are none at this time.

    ## Deployment

    Here we might put additional notes about how to deploy on various systems. For now, put a note that we're testing our code on Linux Ubuntu 16.04 LTS. 

    ## Built With

    * [Python](https://www.python.org/) - The coding language used

    ## Contributing

    Here you could make notes about how others might contribute to your code. For right now, a friendly message saying you'll accept any and all help from other coders would be great!

    ## Authors

    * **Your Name** - *Initial work* - [YourWebsite](https://example.com/)

    ## License

    This project is licensed under the GNUv3 - see the [LICENSE.md](LICENSE.md) file for details

    ## Acknowledgments

    * Hat tip to anyone who's code was used
    * Inspiration
    * etc

    When you finish, click the green Commit changes button at the bottom of the screen.

    Generally, we don’t want to use Github as a development tool. Just for viewing. But to get our README.md started, this is fine. From now on, we’ll only add to our repo from the command line.

    At the top of the screen, click on your username to return to your homepage.

    You should see your repository mycode

    Try following the Alta3 account, and one of the Alta3 Instructors. Navigate to: https://github.com/alta3

    On the left hand side of the screen, click follow.

    Navigate to: https://github.com/rzfeeser

    On the left hand side of the screen, click follow.

    You’ll now see activity by the owners of these accounts. You might try asking some fellow students for their usernames.

    Now we want to sync our command line (where we run git) with GitHub. The goal is to get our code to end up in this mycode repo we created.

    Open a new terminal window.

    The first thing we’ll need to do is generate a new RSA key (essentially a password) and sync this key with GitHub. This will prevent us from having to always type our password.

    student@beachhead:/$ cd /home/student/.ssh

    Create a new unique keypair to use.

    student@beachhead:~/.ssh$ ssh-keygen

    When you are prompted for the file name type /home/student/.ssh/id_rsa_github

    Keep hitting enter throughout this process until the pair has been created.

    Print out to the screen your new public key. We’ll need to paste it into GitHub.

    student@beachhead:~/.ssh$ cat id_rsa_github.pub

    Copy everything that was just printed to the screen to your clipboard (highlight, right-click, copy)

    Back in GitHub, click on your profile icon on the top-right corner.

    Select Settings from the drop down menu.

    Select SSH and GPG Keys on the left

    Click the green New SSH Key button

    Paste the key from your clipboard into Github.

    Click the Add button.

    You’ll likely need to input your GitHub password to complete adding a new SSH Key.

    Check your email and confirm that your key has been added. If your key was formatted incorrectly, it will be rejected immediately or via email. If your key is rejected, try again or ask the instructor for help.

    Back in your terminal, move back to your home directory.

    student@beachhead:~/.ssh$ cd /home/student/

    Let’s add the newly generated ssh key to our ssh-agent. This means it will be loaded and used automatically when we attempt to make ssh connections, i.e. to github.

student@beachhead:~$ ssh-add ~/.ssh/id_rsa_github

    Use this next command to verify that our new key has been loaded and is ready to use.

student@beachhead:~$ ssh-add -l

    Fantastic. Let’s set up git for firsttime use. Replace the name and email address with your own!

    student@beachhead:~$ git config --global user.name "Mona Lisa" student@beachhead:~$ git config --global user.email "monalisa@alta3.com"

    Test that your new key works with github. You should get a friendly message saying your key worked.

    student@beachhead:~$ ssh git@github.com -T

    Customize the command below so that is replaced with your github username. The angle brackets are not needed. If the command doesn’t work, it is because the mycode directory already exists. Move your files out of it, delete it, and then git clone will work (ask instructor if you need help).

    student@beachhead:~$ git clone https://github.com/<github-username>/mycode.git

    You should now have a new folder (mycode) in your home directory. Move into it.

    student@beachhead:~$ cd /home/student/mycode/

    Let’s edit README.md

    student@beachhead:~/mycode$ leafpad /home/student/mycode/README.md

    At the top of your README.md file, within your project description, add a sentence about wanting to learn how to version control projects with git.

    Select: File > Save

    Exit leafpad.

    The following steps are ones you should memorize. You’ll be issuing these commands all the time. First issue git status, which will reveal if you added something and forgot about it.

    student@beachhead:~/mycode$ git status

    Next we’ll describe what we want to add to our repo. We’ll wildcard this, so everything in the ~/mycode/ directory is added.

    student@beachhead:~/mycode$ git add *

    Time to perform a commit. This makes a new version.

    student@beachhead:~/mycode$ git commit -m "First commit to learn about version controlling"

    Now push your new version to Github for tracking.

    student@beachhead:~/mycode$ git push origin master

    Huh. It asks for a username & password (the expection was that the key would take care of this). For now, go up to Github, and see if your README.md file has changed. Remember, we’re don’t want to edit any files in GitHub anymore. Just validate GitHub has the new data.

    You should get in the habit of issuing the following commands each time you have a success, or end for the day.
        git status
        git add /home/student/mycode/*
        git commit -m "reason for commit"
        git push origin master
        Type in username & password

    Becuase we took the time too set up a keypair with Github, we can actually tweak that process. Currently, origin points to the https url: https://github.com//.git , rather than the ssh url: git@github.com:/.git

    We can change where origin points with the following command (from the /home/student/mycode/ directory). Replace <username> with your GitHub username (suchas alta3).

    student@beachhead:~/mycode$ git remote set-url origin git@github.com:<username>/mycode.git

    That’s it! Now when you push to GitHub, you shouldn’t be prompted for a username or password.

    If you ever run into a problem using git / GitHub, let the instructor know. It is critical to start learning to version control code.

    You might want to spend some time clicking around on the following guides. They’re quite short, and although you might not understand what they’re talking about, they’ll begin exposing you to the way we ‘speak’ when using git & verson controlling software. Some getting started guides relating to GitHub can be found here: https://guides.github.com/

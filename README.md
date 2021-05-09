# Git and Visual Studio Code Installation Guide on Raspberry Pi

## Git on Raspberry Pi

### 1.Git Installation.

What you will learn in this guide is how to install and use Git version control software to work on your own projects within Raspberry.

What you are going to learn:


* Install Git on Raspberry
* Create a Repository and upload it to Github



We will use the knowledge of [SSH Raspberry](https://github.com/fullmakeralchemist/raspberrysetup) in this guide using the Raspberry Shell from Putty and we are going to enter the following command.

```
sudo apt install git
```

![installgitMEDIUM](https://user-images.githubusercontent.com/79243784/117558740-73628300-b045-11eb-82ae-bf7c4526751e.png)

![GITINTALED](https://user-images.githubusercontent.com/79243784/117558750-8aa17080-b045-11eb-8085-846e2401320f.png)


### 2.Setting up Git

The first thing we must do is enter our information into Git. This is important, as many people can use Git collaboratively, so you need to know who made changes to which files. You can use your own username and email address.
So we will enter the following commands:


```
git config --global user.name "usuariogit"
git config --global user.email "emailusuariogit@mail.com"
```
![USERGITMEDIUM](https://user-images.githubusercontent.com/79243784/117558774-b58bc480-b045-11eb-9800-b9f4235b6d05.png)

![emailgitMEDIUM](https://user-images.githubusercontent.com/79243784/117558776-bb81a580-b045-11eb-95cc-79aa8c1464dd.png)

Next, you need to tell Git which text editor you want to use. If you don't have a favorite editor, you can simply type:

```
git config --global core.editor nano
```
![EDITORmedium](https://user-images.githubusercontent.com/79243784/117558783-c76d6780-b045-11eb-943c-9475f75f3aa7.png)

### 3.Creating our first project
Do you want to start a new project? Maybe it's a bot like Jarvis that watches over you at all times. You will need a directory on your computer for all your files, so the first thing to do is create that directory.

In the terminal, you can use the ls command (list the contents of the current directory) to check the folders and files.
In the terminal, you can use the cd (change directory) command to change a new directory.
In terminal, you can use the command mkdir (create directory) to create a new directory.

```
ls 
cd Desktop
mkdir snitch-sniffer
cd snitch-sniffer
```
![mrkpruebaMEIDUM](https://user-images.githubusercontent.com/79243784/117558794-e966ea00-b045-11eb-990e-1e088519eb0d.png)

You can then create a file that will tell people what the project is about. You can use any text editor to do this, like Notepad or later when we have the Visual Studio Code you can make a second file to practice. Create a file called README.md. The .md extension stands for Markdown, which is a markup language. You can learn more about Markdown [here](https://daringfireball.net/projects/markdown/). To create a file from the Raspberry Shell we will use the command:

```
nano README.md
```
Now we can enter text in our file, to save the file "Ctrl + O" and finally to exit the editor "Ctrl + X".

A second option is to use previous knowledge of [Wireless Setup](https://github.com/fullmakeralchemist/raspberrysetup), to enter via VNC and create the file. As in any computer we will use right click, new option and give a name and extension to the file.

I put the following text in the README.md file


```
# The Golden Snitch Sniffer
This is a project that uses multiple long-range ultrasonic sensors to find and track
an object flying in three-dimensional space. It displays the object's coordinates,
speed, and trajectory through a VR headset.
```
![README](https://user-images.githubusercontent.com/79243784/117558806-fdaae700-b045-11eb-8f70-ecf780be6175.png)

![textREADMEMEDIUM](https://user-images.githubusercontent.com/79243784/117558811-00a5d780-b046-11eb-9b84-fc13d1d212ee.png)

Your file should have been created and will now be located in your directory. You can type in the terminal to see a list of files the following command.

```
ls
```

At the moment, the directory is like any other on your system. Now you need to do the version control part. This is known as a Git repository and it takes the form of a hidden directory that keeps track of all changes in the working directory. Enter the following to create the repository, which from now on will only be called the repository:

```
git init
```
![gitinitraspberry](https://user-images.githubusercontent.com/79243784/117558825-10bdb700-b046-11eb-995f-2db9bf133eb9.png)

If you retype ls, nothing will appear to have changed. However, you can use `ls -a` to see all hidden files and directories.

Now you should see something like this in your terminal window:

`. .. .git README.md`

That .git directory is the skeleton of the repository. You can take a look inside by typing the following.

```
ls -a .git
```

So now you have the magic backpack part, but you haven't added anything to it yet. That README.md file has not yet been placed in the bag. You have to tell Git that you want to add the README.md file to the repository. To do this, simply type:

```
git add README.md
```
However, sometimes it is easier to add everything to the repository, rather than adding individual files. To do this, you can write:

```
git add --all
```

Now Git knows that it needs to keep track of all the changes that happen to the README.md file. You can view the status of your repository at any time by typing:

```
git status
```
The answer above tells you that the README.md file has not yet been committed. This means that even though Git knows about the file, it doesn't have any of its contents stored yet. The easiest way to commit is by typing:

```
git commit -am "add README.md"
```

This commits all the changes you have made to the directory in the Git repository and adds a message saying what you did. The message can be anything really, but it is better to be fairly short but descriptive of what has changed.

### 4.Trabajando con un Github

Now that you know how to do the basics in Git, it's time to learn how to use it to its full potential - use it to share your work and collaborate with others.

There are many services that will host your Git repository for free. GitLab is one of those services and BitBucket is another. In this resource, you will be using GitHub, which is one of the most popular services.

The first thing to do is sign up for an account at [GitHub](https://github.com/join?source=header-home) and just choose the free plan.

Now that you have an account, you can create a snitch-sniffer repository on GitHub. Find the New Repository button and click on it.

![new-repo](https://user-images.githubusercontent.com/79243784/117558864-46fb3680-b046-11eb-9208-31c6c735a6e8.png)

Give a name and description to the repository and click the Create repository button.

![gh-repo](https://user-images.githubusercontent.com/79243784/117558869-50849e80-b046-11eb-8b25-8f79b01289c4.png)

Next, an instruction page should appear.

![instructions](https://user-images.githubusercontent.com/79243784/117558872-55495280-b046-11eb-94e3-d318528645e9.png)

Since you already have a repository ready to push to GitHub, then all you need to do is make sure you are in your project directory and type:

```
git remote add origin git@github.com:HarryPotter/snitch-sniffer.git
```
and later:

```
git push -u origin master
```
If you search GitHub, you should now be able to see your repository, along with the README.md file that is displayed and that you wrote.

![gh-repo](https://user-images.githubusercontent.com/79243784/117558894-80cc3d00-b046-11eb-9ef5-9d7d8952c012.png)

Every time you make changes to your project and want to push them to GitHub, you can write:

`git push origin master`

If you are working on a different branch you would write:

`git push origin <branch-name>`

To know more about Git in Raspberry I recommend you go to [Getting started with Git](https://projects.raspberrypi.org/en/projects/getting-started-with-git).


## Install Visual Studio Code on Raspberry.

### 1.Installation
Thonny IDE (Integrated Development Environment) bundled with the latest version of Raspberry Pi OS. Thonny comes with Python 3.7 built in, so nothing needs to be installed.

As a personal preference my favorite IDE is VS CODE, for some projects like Apps in Flask, Bots and Tensorflow, I feel more comfortable working in the VS interface.

The great news is that VS Code is now available as part of the Raspberry Pi OS apt packages. Launch the Raspberry Pi terminal and run the following commands:

```
sudo apt update
sudo apt full-upgrade
sudo apt install code -y
```
The installation will take a while, after finishing, you can access through VNC and check that the installation was successful.

![visualRASPBERRYmedium](https://user-images.githubusercontent.com/79243784/117558901-90e41c80-b046-11eb-9172-92fa7f89775a.png)

Ready with this, we can start working with VS CODE and Git, try to use what you learned in this guide, to create a second repository with VS.

You can also check the repository for this post on my Github.

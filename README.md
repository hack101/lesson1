##I. Getting started

### Introduction

Hello everybody, welcome to the first tutorial in our series on the fundamentals of making a website. Over the course of these 5 lessons, we will cover the basics of how websites work, what you need to know to get started, and setting up a good workflow for developing a website of your own. 

We assume that you're not completely new to programming - you should at least have the background that an introduction to programming course like COMP 202 would give you. Some familiarity with your computer's developing environment is a plus - we will be working with the command line from the beginning. I will also be teaching from a unix environment, so if you are using Windows, you may find it harder to follow along with your own computer. However, the concepts will largely remain the same.

These courses are aimed at people who have started to pick up the tools for programming but are unsure how to take on larger projects. Making a website can seem intimidating - modern web development includes a lot of different tools, which can make the task of creating a website yourself seem frighteningly complex. Our goal is to show you that you can work your way into this world with what you already know. Don't let the vastness of modern web development scare you away - once you know some basics the rest will seem much more tractable.

### Theory

Before we begin getting into the nitty-gritty, it's a good idea to have a (basic) conceptual image of what a website is. We'll brush over this quickly, and get into more details in the final tutorial, once you have more concext for them. At the moment, what you need to know is that a website is basically a set of files and folders on a computer somewhere. This is what you need to know when you're making a website, because you'll be making these files.

There are two important parts of the equation: the client, and the server. You are the client - well, more specifically, your web browser, be it Chrome or Firefox or whatnot, is the client. But it suffices to consider the user and their browser as the client. The client wants something: the webpage. When you type a website's URL into your browser, you are asking for the website at that URL. When you press enter, your browser sends out a request for the website at that address.

This is where the server comes in. The infrastructure of the internet matches the address you typed in to a server somewhere. That server is a computer which holds the content of the website, represented in different types of files. So when you type in a URL, your browser asks the server for the files that make up that website. And if the server is available, it sends those files back to you, the client. These files are just a bunch of text, right? Some of them might look like this:

````html
<html>
  <head>
    <title>My first website</title>
  </head>
  <body>
    ... and so on
````

This is a type of file - an HTML file, to be exact - which represents some structure for a webpage. Your browser knows how to read this type of file, and it knows how to turn the weird format into the visual representation of the website.

So a website is a bunch of files on some server, and when you visit that website, your browser asks the server to see those files so it can draw them for you.

Here's some vocabulary: we say that the server "hosts" the website, or hosts the files that make up the website. Today we'll start writing those files, and let someone else host them for us (for free!). In later tutorials we'll learn more about hosting, and get a little more involved.

### So about those files

The physical aspect of programming is basically writing a lot of files (the mental part is mostly figuring out what to name them). One side-effect of this fact is that programmers tend to spend a lot of time thinking and talking (arguing) about what they'll write these files with. What we write these files with are text editors. These are programs whose purpose is to make writing a lot of text as painless as possible. As I mentioned earlier, it's assumed you've done some programming before, so you're probably familiar with the concept of a text editor. Mostly, you know that Microsoft Word or something like that is not an acceptable text editor :)

We will be using Sublime Text as our text editor for these tutorials. Sublime Text is a popular, modern text editor, so that's one reason we will use it. (Footnote: Another reason is the fact that if I chose my old editor of choice (vim), someone would ask me why I don't use emacs instead. If neither of those words make sense to you, consider yourself blessed that you haven't been pulled into the holy war that rages between users of vim and users of emacs). Hopefully you've got Sublime Text installed already, so you're ready to start writing some files.

### Hello web

Let's make the first file of our website. Start off by creating a new folder somewhere on your computer that will hold our website. Name it whatever you'd like. Inside this folder, create a file called `index.html`. When you type in a URL that doesn't end with a filename - for example, `www.google.com/`, you are essentially asking the server for a folder, not a particular file. But a web page is represented by a file, so the server assumes you are asking for some `index.html` - a file that holds an index (list) of all the files in that folder. If you make your own `index.html`, the server will send that back. This is true for most servers.

Inside `index.html`, we will write the following:

````html
<html>
  <head>
    <title>Hello world</title>
  </head>
  <body>
    I am a website?
  </body>
</html>
````

Save the file, and then open it in a browser. There are a few ways of doing this - the easiest if you are using Sublime Text is to right click and select "Open in Browser". You can also find the file in your filesystem (using Finder on a mac, or whatever) and choose to open it with a browser. Or, you can find the path to the file, and type that in the address bar of your browser, like a URL. When you open the file, you should see a page, empty but for the existential question "I am a website?" If you named the folder that contains our `index.html` something like `website`, then the filepath will look like `.../website/index.html` in your address bar.

![You tell me](http://i.imgur.com/P3PxgyS.png)

An HTML file like our `index.html` is made up of what we call "tags". That's the stuff wrapped in `< >`. Tags have specific meanings that your browser understands. Importantly, tags should come in pairs: opening tags, which are just a word inside the `< >`s, and closing tags, which are the same word, but with a / in front. Some particular tags do not come in pairs, and we will see those later, but for the moment, please keep in mind that when you write an opening tag, _you must add a closing tag_. The reason I am being so emphatic about this is because if you do not close a tag, your browser will still give you a webpage back _without telling you it may be wrong_. If you don't close a tag, the browser will still try to render a webpage, but the result might not be what you wanted. When things fail on the web, they do so silently.

In the interest of time, I will not go into what every individual tag does. Just from comparing the file to the resulting webpage, you can deduce that the `title` tag holds the text that goes in the tab for that page, and the `body` tag contains the content of the page that you see. There is a wealth of resources on the web that can teach you the basics of tags, what tags there are, etc. The purpose of this tutorial is to walk you through the first steps so you have a mental framework to build upon with your own outside reading.

One great resource for this is the [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/), and you can find their content on HTML [here](https://developer.mozilla.org/en-US/docs/Web/HTML).

### Save points

Over the next few tutorials we will be building upon this basic website. This means we will be making changes to the file we already have and creating new files as well. Thus, the state of our project will be different over time. We might make some changes we don't like, and at that point we'll probably want to go back to where we were before. Of course, every time we save a file we overwrite what it contained in the past, so we lose past state - which is bad if we want to go back to that state. You might remember solving this problem in high school by saving multiple copies of one of your projects in different states: "essay", "essay1", "essay_good_copy", "essay_final", "essay_FINAL", "essay_ACTUALLYFINAL" and so on. There is a better way, and that way is git.

Git essentially allows you to create save points for your project, which are stored for later use. You can rewind your project to one of these save points if you mess up, or even branch off into two different directions if you want to try different ways of doing things. You can also save the history of your project to other places, so multiple people can work on the same project, or you can have a backup of the entire project history on another computer in case yours breaks. Git has a large number of uses, and we will only use it for the absolute basics: saving project history, and storing that history somewhere else.

There is a nice set of slides from a talk last year about git given by Wendy Liu, a former student (and the person behind [WikiNotes](http://www.wikinotes.ca)). You can view those slides [here](https://speakerdeck.com/dellsystem/git-and-github-tips-and-tricks) if you want more of an idea what git can do. Once again, I will not go into the specifics of git beyond a few basic commands, but there are many resources online that can tell you more.

Hopefully you've all installed git beforehand, so we can jump right into using it for our project. To begin, find the folder you created for the website in the command line, and type in `git init`. This will create a new "repository" for your project - a repository being a place where things are stored, in this case your project history. At any point, git will track some set of files you tell it to. When you change these files, git will notice. Now the "save points" we talked about earlier are called "commits" in git. A commit is a set of changes to files that you want to logically group together. For example, say you add a new feature to your website: that feature consists of a number of changes to files, files being created, etc. You group those changes and commit them, along with a message that says something like "Add new feature".

So git keeps track of changes to files since you last committed them, and you tell git which changes you want to commit. Then when you've told it all the changes you want for a commit, you can create the commit with those changes. Let's do that now. Type in `git status` to see the status of our project. There will be a section called "Untracked files" - in that section will be `index.html`. We can tell git to start tracking it by typing `git add index.html`. Now type in `git status` again: `index.html` will now be in the section "Changes to be committed". This section holds everything that will be added to a commit when we make it. Since there's nothing else to add at the moment, let's make the commit.

Type in `git commit -m "Create index.html"` and press enter. Git will create a commit containing your file, along with a "commit message" describing what the commit does. The `-m` lets us add that message in this command, but if you want to type something longer you can just type `git commit` and git will open up your default text editor (probably vim) and let you enter your commit message there. Now that we've made a commit, when you look at the status again, it will say "Working directory clean" - there are no new changes. If you edit `index.html`, you can look at the status again and see that git noticed you made some changes. You can add these to a commit by doing `git add index.html` again, but it's easier to type `git add -u`, which means "add all changes from files I'm tracking to be committed". The `-u` is for "update".

### Github and hosting

So now we have a (very rudimentary) website, and we've saved our progress on it with git. The final thing we will do today is push our saved history to another source, so other people can view our progress, and also so we can host it somewhere on the internet. At the moment, only you can see your website, because it is hosted on your computer. If your friend wants to see it they will need to be content with seeing it on your screen. For this, we will use Github. Github will store your project history for you, and also host very basic websites as well.

First, let's push to Github. Log in to www.github.com, and create a new repository. It will give you instructions for pushing to the new repository it creates - follow those.

Once you've pushed, you should be able to see your files on the github website!

Now we can also use Github to host the website.


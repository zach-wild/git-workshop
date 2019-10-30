https://github.com/zach-wild/git-workshop.

### Downloading this repository
First make a new directory to initialize your git project in.
```sh
$ mkdir git-workshop
$ cd git-workshop
$ git init
```
Now we have intialized a git project in our directory. The next step is to add a remote. We will call this remote origin and the url will be that of the fork we just created. A remote is just a reference to a git repository.
```sh
$ git remote add origin https://github.com/<your-username>/git-workshop.git
```
Now that we have referenced our newly created repository we can download it do our local machine and start making changes to it. The fetch command is used to download all of the git objects from the repository; more detail (https://www.atlassian.com/git/tutorials/syncing/git-fetch).
```sh
$ git fetch origin
```
Now that we have all of the changes we want to incorporate them into our local git repository. The merge command joins the git history of two branches, we'll talk more about branches later. In our case this will be the origin/master branch we fetched and the master (default) branch that was created when we ran git init.
```sh
$ git merge origin/master
```
Now we have a local copy of this repository that we can make changes to. There is also an easier way to do all of this which is to instead clone a repository.
```sh
$ git clone https://github.com/<your-username>/git-workshop.git
```
This will perform all of the steps we just did with one command. But now lets makes some changes to the project. 

### Making some changes to the website
The whole point of git is to keep track of the changes made to a project. We'll run a quick command to look at the history of changes made to this project.
```sh
$ git log
```
We'll see that we have two commits. Each commit has a hash (if you want more information on this read this (https://blog.thoughtram.io/git/2014/11/18/the-anatomy-of-a-git-commit.html) , author, date, and commit message. We can get more information about each commit by adding additonal parameters to the log command (https://git-scm.com/docs/git-log). We'll run one version which will give us some high-leve information about what was done in each commit.
```sh
$ git log --stat
```
Now that we can see what files we're changed during each commit, lets do something similar. Open the project in your favorite text editor and we'll change some of the files. Feel free to make whatever changes you'd like. I'm going to change the joke on the jokes page from
```html
<div id="navbar">
      <a href="./index.html">Home</a>
      <a href="">Jokes</a>
  </div>

  <h1>This page is under construction.</h1>
  <br>
  <h1>... Watch your head.</h1>
</body>
```
to
```html
<div id="navbar">
      <a href="./index.html">Home</a>
      <a href="">Jokes</a>
  </div>

  <h1>That was a great joke.</h1>
</body>
```
Now that we've made whatever changes we want to save these changes. If we run the status command we can get an idea of what has changed about the project since the last commit.
```sh
$ git status
```
We'll see files that have been changed and it also mentions that no changed have been added to commit. We can add changed to commit with the add command. 
```sh
$ git add jokes.html
```
Now if we run git status again we'll see that it says that we have modified the jokes.html file and that this change is ready to be committed. So now we are going to create a commit. 
```sh
$ git commit -m 'Included better jokes'
```
Now if we check our git history we will see that our newest commit is included.
```sh
$ git log --stat
```
Now that we have made some changes to our project we would like to sync up our local and remote repositories. We are going to push the changes we made, the commit, to our remote repository. Remember that we created a reference to our remote repository with the origin remote. Similar to how we donwloaded from this remote we can upload to it.
```sh
$ git push origin master
```
We should recieve a permission denied error.

### Configuration
We are going to follow this tutorial to configure git to work with your github account. (https://kbroman.org/github_tutorial/pages/first_time.html)

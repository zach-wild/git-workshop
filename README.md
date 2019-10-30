https://github.com/zach-wild/git-workshop.

### Cloning this repository
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


Now we have a local copy of this repository that we can make changes to.

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
Now that we've made whatever changes we want to save these changes. 

### Configuration
We are going to follow this tutorial to configure git to work with your github account. (https://kbroman.org/github_tutorial/pages/first_time.html)

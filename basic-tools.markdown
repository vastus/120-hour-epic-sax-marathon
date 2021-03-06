% Basic Tools
% 120 hour epic
% sax marathon

## Synopis

- the development environment
- how to submit exercise answers

## First things first

To successfully work through this course, you need to do the following
things:

- install Java
- install a sane editor: Light Table, Vim or Emacs
- install Git
- install Leiningen
- make sure to have a github account
- inform the teachers about your github account name
- read very carefully the submission instructions

## Java

Clojure runs on JVM, so you need to have the Java JDK installed. On
Linux this is easily done using the distribution's package manager.

On Windows you need to download the latest JDK from Oracle's site and
install it. You also need to add the JDK bin directory to the Path.
Right click Computer, select Properties, select Advanced system
settings, select Environment Variables and Edit the Path to contain
the `bin` directory of the JDK installation usually found under
`Program Files`. Don't hesitate to ask if you encounter any problems.

## Editor

As a lisp, Clojure requires some support from the text editor to be
pleasant to write. Luckily a guy named Chris Granger has started a
project to create The editor called Light Table. It's still quite
alfa, but works nicely for your purposes during this course.
[Check it out][LightTable]. When in doubt, use this.

Light Table is more or less like an ordinary editor with some IDE like
features. The thing that sets Light Table apart is the Instarepl. It
is a tool in which you can write Clojure code, run it and instantly
see the results. This is a great environment to test ideas and also to
solve the exercises. Many think that working in the repl is one of the
best things in Clojure developement.

When you open Light Table, you get a Welcome screen and menus in the
left hand side. To get going, you can open an Instarepl by selecting
`command`, writing `open instarepl` to the box and selecting the
presented choice. This opens a tab to which you can start writing
Clojure code.

Not suprisingly, both Vim and Emacs have good plug-ins to work with
Clojure. For the basics, one should install the clojure-mode from the
Emacs package manager. For a more complete set of tools we can
recommend [Emacs Starter Kit][EST]. In Vim, [VimClojure][VimClojure]
provides you with the necessary goodies.

## Your very own butler

[Leiningen] is a project management tool for Clojure projects. It
handles various tasks related to projects, including building the
project, declaring and fetching dependencies, opening an interactive
session inside the project, and other such things.

Here's the instructions for installing Leiningen in Linux:

1. In your home directory, create a directory called `bin` if it does
   not exist all ready.
  
    ~~~ {.sh}
    cd ~
    mkdir bin
    ~~~

2. Add this directory to your $PATH. If you are using Bash, put the
   following inside the file `~/.bashrc`. If you are using some other
   shell, do this where you would normally do these kind of things. If
   you don't know what shell you are using, you are using Bash.

    ~~~ {.sh}
    export PATH=$PATH:~/bin
    ~~~
    
3. Source the `~/.bashrc` file to apply the changes.

    ~~~ {.sh}
    source ~/.bashrc
    ~~~

3. Download [this][LeinInstall] script. Put it in the `~/bin`
   directory created in step 1
  
4. Make the script you just downloaded executable.

    ~~~ {.sh}
    chmod +x ~/bin/lein
    ~~~

5. In any directory, issue the command `lein help`. This will first
   download the rest of Leiningen. After the download is complete you
   get a list of services provided by Leiningen.

In Windows you need to do the following:

1. Download the GNU wget binary from [here][wget] and place it in a
   appropriate directory.
   
2. Download the Leiningen [batch file][LeinInstallWindows] and place
   it in an appropriate directory (same place as wget is fine).
   
3. Add the previous directories to Path. Right click Computer, select
   Properties, select Advanced system settings, select Environment
   Variables... and Edit `Path` to contain the directories.
   
4. Open `cmd.exe` and run `lein self-install`.

The table below contains some important Leiningen commands.

Command         Description
-------         -----------
midje           Run all [Midje] tests.
repl            Open an interactive Clojure session.
new             Create a new Clojure project.

To get more information about a command, run `lein help <command>`.

The heart of every Leiningen project is the file `project.clj` at the
top level of the projects directroy tree. It contains information
about the projects name, version and dependecies among others.

## Git

[Git][Git] is an distributed version control system. A fancy name for
a tool that keeps track of changes made to files under a directory
tree. We use this tool to distribute pre-made Leiningen projects in
which you can complete the exercises of every chapter. You also use
Git to submit your answers. If you have any problems with Git, ask.

To install Git on Linux, use your distribution's package manager. In
Windows, point your browser to [http://git-scm.com/][Git], where you
can find both the binaries and a comprehensive documentation. On
Windows it's the easiest to use the Git-bash that comes with Git.

There are three basic commands that you need to know to successfully
submit exercises:

- `git clone` will copy a repository
- `git commit -a -m "message goes here"` will inform git about all the
  changes you made. The message should summarise what has changed.
- `git push` will upload the changes previously commited to github

## How to submit answers to exercises

At the start of every chapter, you should go to [Github][Github] and *fork*
the chapters repository. There will be a link to the appropriate repository at
the beginning of every chapter. You then *clone* your **own** fork of the
repository and start working with the exercises when you encounter them amongs
the material. You create *commits* and maybe *push* them in to your own fork
while working. You also run the tests with `lein midje` to see if they pass.

When you want your answers graded, you push all of your work with `git
push`. You then go to Github and send a *pull request*. At this point,
[Travis][Travis] kicks in. It runs the tests for your
code and then comments on the pull request whether the tests passed or
failed. A link is also provided to see the nitty-gritty details.

If you didn't get all the tests to pass on the first go, don't worry,
you can try again. Just make modifications to the code, create a
commit, and push. The pull request will be updated, Travis will rerun
the tests and a new comment about the build status will be posted. You
can keep trying as many times as you want.

We read the pull requests now and then and sometimes comment on the
code. You should also check your pull requests to see if something
needs to be fixed before points can be awarded. If all tests passed
and everything looks good, we will announce your points on the
comments and close the pull request. After the deadline, all the pull
requests will be closed, and you will get points for those exercises
that you succesfully completed.

### Tell us who you are

For this system to work, we need to know who you are. If you haven't
already, please fill out [this form][Form].

<alert>

The pull requests are visible to everyone. If you don't want your grading to
be public, create an anonymous Github account and pass the name of that to us.

</alert>

### Be prepared

Lets go through the first part of this process to be ready for the next
chapter.

1. Go to the Github page of the repository of the next chapter. Here is the
   [link](https://github.com/iloveponies/training-day).

2. Click the Fork-button near the top-right corner of the page. You will be
   asked to login if you haven't done so already.

3. The Github page of your fork will open. This is the repository you want to
   clone. Click the button that says HTTP and copy the link from the box. Then
   issue the following command with **your** version of the link. Your Github
   login information will be requested.

    ~~~ {.sh}
    git clone https://github.com/<my-account>/training-day.git
    ~~~
    
4. A directory `training-day` will be created. Go inside the directory and
   issue `lein midje`. You should see output that tells you that every test in
   the project has failed.

        cd training-day
        lein midje
   Instead of `lein midje`, you can issue the command
   
        lein midje :autotest
   This starts a loop which runs the tests again every time you make changes
   to any of the projects files. A very handy feature, as running plain `lein
   midje` has a pretty long startup time.
   
5. You are now ready to start working with the exercises. When ever you
   encounter an exercise in the material, open the file `src/training_day.clj`
   and fill the appropriate function. Run `lein midje` often to see if the
   tests pass.
   
[Proceed, young padawan. →][next]

[Form]: https://elomake.helsinki.fi/lomakkeet/42235/lomake.html
[LightTable]: http://www.lighttable.com/
[EST]: https://github.com/technomancy/emacs-starter-kit
[VimClojure]: https://github.com/vim-scripts/VimClojure
[Git]: http://git-scm.com
[Github]: https://github.com
[Leiningen]: https://github.com/technomancy/leiningen
[LeinInstall]: https://raw.github.com/technomancy/leiningen/stable/bin/lein
[LeinInstallWindows]: https://raw.github.com/technomancy/leiningen/stable/bin/lein.bat
[Midje]: https://github.com/marick/Midje
[Ubuntu]: http://ubuntu.com
[Vim]: http://vim.org
[next]: training-day.html
[vm]: http://cs.helsinki.fi/ilmari.vacklin/ClojureBox.zip
[VirtualBox]: http://virtualbox.org
[wget]: http://users.ugent.be/~bpuype/wget/#download
[Travis]: http://travis-ci.org

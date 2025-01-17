django-getting-started
======================

Step by step guide to getting started with Django development on OS X

This is my preferred setup, developed over my years as a programmer. There are many options, which 
I will omit here for the sake of simplicity, but feel free to modify to suit your needs.

Notes:

1. Any line that is preceeded by a '$' means that is a command to be typed into Terminal.
1. If you've completed a given step in the past, you can skip that step and go to the next.
1. Any value that is in angle brackets and capitalized (e.g. <SOME_VALUE>) is a placeholder and must
be replaced by an actual value.


Development Environment Setup
-----------------------------

1. Install XCode from the Apple website.
> XCode download: https://developer.apple.com/xcode/downloads/
>
> Detailed steps available here: http://railsapps.github.io/xcode-command-line-tools.html

1. Install the command line tools. This allows you to compile packages from source.
> Open Terminal app (I recommend adding it to your dock, as you will need it often)
>
> At the prompt, enter "gcc":
>
>     $ gcc
>
> If you don't already have the command line tools, you will be prompted to install them.

1. Install homebrew. This gives you easy access to useful system packages. Up-to-date install
instructions can be found on the homebrew site: http://brew.sh/
> In Terminal:
>
> $ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

1. Familiarize yourself with a command line editor. Emacs and Vim are popular choices.
> Emacs basics: http://mally.stanford.edu/~sr/computing/emacs.html
> Vim basics: http://vim.wikia.com/wiki/Tutorial

1. Ensure that commands from homebrew packages are found before system commands. You can do this by
editing your .bashrc file. In Terminal, enter the following:
> $ cd ~
> $ emacs .bashrc  # Could also use vim
> export PATH=/usr/local/sbin:/usr/local/bin:$PATH  1. Add this to the bottom of the file
> Save and exit

1. Source your changes to .bashrc into the current shell. In Terminal, enter the following:
> $ . ~/.bashrc

1. Verify that homebrew is installed correctly. In Terminal, enter the following:
> $ brew doctor

1. Install git using homebrew. In Terminal, enter the following:
> $ brew install git

1. Make a directory to hold all your programming projects. I call mine "Development" and I put it
in my home directory.
    
1. Sign up for a GitHub account: https://github.com/join
    

Python Environment Setup
------------------------

1. Install python 3 using homebrew. This is the latest version of python, and while much existing
code is still written in python 2, for new projects it is best to use python 3. In Terminal, enter
the following:
> $ brew install python3

1. Verify the correct python3 is now on your path. In Terminal, enter the following:
> $ which python3  # Should be "/usr/local/bin/python3"

1. Install virtualenv and virtualenvwrapper. The virtualenv package allows you to have individual
environments for every python project, separate from the system package installs. The 
virtualenvwrapper package is a utility to manage your virtualenvs. It keeps the virtualenvs separate
from your code and also provides useful operations on virtualenvs.
> $ sudo pip3 install virtualenv virtualenvwrapper

1. Add virtualenvwrapper configuration to your .bashrc file. You can do this by
editing your .bashrc file. In Terminal, enter the following:
> $ cd ~
>
> $ emacs .bashrc  # Could also use vim
>
> Add the following 3 lines:
>
>     export WORKON_HOME=$HOME/.virtualenvs
>     export PROJECT_HOME=$HOME/Development
>     source /usr/local/bin/virtualenvwrapper.sh
>
> Save and exit

Django Project Setup
--------------------

1. Log in to GitHub and create a new repository.
> Click the '+' in the upper right and select "New repository"
>
> Enter repository name ("starter") and description ("Starter Django project")
>
> Select "Initialize this repository with a README"
>
> Under .gitignore select "Python"
>
> Under license select "MIT License"
>
> Click the "Create repository" button
>
> On the right-hand side, select the value in the HTTPS clone URL box and copy it

1. Clone your project. Open Terminal, and do the following:
> $ cd ~/Development
>
> $ git clone <VALUE_FROM_GITHUB> # Paste in the value you copied above

1. Make a virtualenv and install django-toolbelt, which includes Django and useful packages for
deploying a Django project to Heroku. In terminal:
> $ mkvirtualenv starter --python=python3  # Create a python3 virtualenv
>
> $ pip install django-toolbelt

1. Initialize your project as a Django project. In Terminal:
> $ cd starter
>
> $ django-admin startproject starter .

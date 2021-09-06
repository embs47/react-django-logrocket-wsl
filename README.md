# React-Django Project from LogRocket in WSL 2

A sample project created as guide to create a React and Django app.
This development environment for this project was setup using WSL 2.
The following includes the steps in creating the project:

## General step and guide
1. Install WSL 2. See guide [here](https://docs.microsoft.com/en-us/windows/wsl/install-win10).
2. Install nvm, node.js, and npm. See guide [here](https://docs.microsoft.com/en-us/windows/dev-environment/javascript/nodejs-on-wsl).
3. Start django project.
    * See guide [here](https://docs.microsoft.com/en-us/windows/python/web-frameworks) for setting up python environment.
    * See guide [here](https://docs.microsoft.com/en-us/windows/dev-environment/javascript/react-on-wsl) for installing react.
    * See guide [here](https://blog.logrocket.com/creating-an-app-with-react-and-django/) for the whole django and react app tutorial. 

## Detailed steps with commands
1. Install WSL 2.
    * Enable the Windows Subsystem for Linux
        ```bash
        dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
        ```
    * Check requirements for running WSL 2 via **Windows logo key + R, type winver, select OK**
    * Enable Virtual Machine feature
        ```bash
        dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
        ```
    * Download the Linux kernel update package
    * Set WSL 2 as your default version
        ```bash
        wsl --list --verbose
        wsl --set-default-version 2
        ```
    * Install your Linux distribution of choice **eg. [Ubuntu 20.04 LTS](https://www.microsoft.com/en-ph/p/ubuntu-2004-lts/9n6svws3rx71?rtc=1#activetab=pivot:overviewtab)**
    * Open Ubuntu terminal and check release
        ```bash
        lsb_release -a
        wslfetch
        ```

2. Install nvm, node.js, and npm.
    * Install cURL
        ```bash
        sudo apt-get install curl
        ```
    * Install nvm
        ```bash
        curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
        ```
    * Install Node.js and the latest stable LTS release
        ```bash
        nvm install node
        nvm install --lts
        ```
    * Verify installations/versions
        ```bash
        command -v nvm
        node --verison
        npm --version
        ```

3. Start django project.
    * Install pip
        ```bash
        sudo apt update
        sudo apt install python3-pip
        ```
    * Install venv
        ```bash
        sudo apt install python3-venv
        ```
    * Create/navigate to project folder (e.g. **~/workspace/react-django-project**)
    * Create and activate virtual environment
        ```bash
        python3 -m venv .venv
        source .venv/bin/activate
        ```
    * Open vscode via ```code .```
    * Install django, 
        ```bash
        python3 -m pip install django djangorestframework django-cors-headers
        ```
        or install requirements
        ```bash
        pip install -r requirements.txt
        ```
    * Check django version
        ```bash
        python3 -m django --verison
        ```
    * Create django project and app
        ```bash
        django-admin startproject django_react_proj .
        python3 manage.py startapp students
        ```
    * Build the React app
        ```bash
        npx create-react-app students-fe
        ```
    * Navigate to React app folder and install dependencies
        ```bash
        npm install bootstrap reactstrap axios --save
        ```
    * Start app (*make sure to be in the react app folder directory and django server is running*)
        ```bash
        npm start
        ```

## Git configuration
    
    $ sudo apt-get install git
    $ git --version
    $ git config --global user.name "name"
    $ git config --global user.email "email"
    $ git config --global color.ui auto
    $ git congig --global -l
    // naviagte to project directory
    // add .gitignore and README file
    $ touch .gitignore
    $ touch README.md
    $ git init
    $ git status
    $ git add .
    $ git commit -m "Initial commit."



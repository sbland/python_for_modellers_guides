Python Environment Setup
========================

This is a tutorial series on setting up a Python Environment for Researchers. 
Note this tutorial uses Python and Pip instead of Anaconda.

# Key Steps

1. Install a command line tool.
2. Check your python version from the command line.
3. If you have no python installed or incorrect version install using the instructions below.
4. Install GIT if not installed
5. Git pull the required project repository
6. Setup and activate a virtual environment
7. Install the reqired python dependencies
8. Running the model




# 1. Install a command line tool

Windows has 2 built in command line tools; cmd and PowerShell.
There are also Unix based shells that can make some tasks easier including GitBash

We will use powershell for this tutorial.

Some useful command line commands:

 - `cd <PATH>` this will navigate to the path
 - `ls <PATH>` this will list the contents of the path
 - `mkdir <PATH>` this will make a new directory

# 2. Checking the Python version from the command line

To check your version in the command line type `python -V` (Notice the uppercase V).

If this displays the correct version you can continue to **step 4**.

You can also check the available versions with `py -0`. This will list installed versions. To use a specific version use `py -3.9` replacing `3.9` with the version number.

If the correct version is unavailable go to **step 3** or check **Troubleshooting Python Install** if you have already installed it.


# 3. Installing the correct version of Python

For windows you can run the Python installer from the Python home page `https://www.python.org/downloads/`. Ensure you select the **Add Python 3.9 to PATH` checkbox.

Once installed you need to restart the command line tool then follow step 2 again to check it is working.

# 4. Checking and Installing GIT

GIT is a tool for version control. The GIT command line tool can be used to version control a directory and link it to websites such as Github, Gitlab or Bitbucket where it can then be downloaded from elsewhere.

To check if git is installed and linked to your command line type `git --version`. If you get an error stating not a command install it from `https://git-scm.com/downloads` then restart your command line.

# 5. Git pull the required Repository

To obtain the files for the project go to the project git page then find the url to download (On github this is the green `Code` button). You will need to use the `HTTPS` link unless you have SSH setup.
Note if you have two factor auth setup your password will be an access token instead of your password.

Run `git clone <REPO_URL>` inside the directory you want to copy to.

# 6. Setup and activate a Python virtual environment

Using a virtual environment in Python is important. It means anything you install will just be installed in this environment so you do not get version conflicts when switching between projects.

To create a virtual environment first type `python -v` to check you have the correct version (You may need to use `python3` instead).
Then run `python -m venv venv`. This will create a new virtual environment called **venv**. To activate the environment (from powershell) type `./venv/Scripts/activate.ps1`. If this has worked you should see `(venv)` at the start of the line.

To deactivate type `deactivate`.

# 7. Install the required python dependencies

Each python project has specific python library dependencies. These are often contained in a requirements.txt file (else specified in the project readme.md).

**Ensure you have activated your python virtual environment first!**

To install individually run `pip install <PACKAGE_NAME>`.
To install from a requirement.txt file run `pip install -r requirements.txt` (replace requirements.txt with the name of the requirements file if needed).

# 8. Running a python model
Instructions for running the model should generally be inside a README.md file at the root of the repository.

To run a python file type `python <FILENAME>`
 
 
 # Troubleshooting python install
 
If you have installed the version and it is not showing up check the below steps.

1. Check if Python is installed but not available in the command line. 
Check the following directories to see if Python is installed. You can either do this from a file browser or by typing `ls "<PATH_TO_DIRECTORY>"` (Note the use of speech marks around the path):

 - `C:\Users\<YOUR_USER_NAME>\AppData\Local\Programs\Python\`
 - `C:\Program Files`

 - If the required version of Python is listed got to `Edit environment variables for your account` by typing this into the windows search. 
 - Go to the path variable in the user variables list then click `Edit...`. Make sure that the path to your python install is in this list.
 - If it is not in the list use `New` to add it. Also add `<python path>/Scripts` to add the associated scripts.


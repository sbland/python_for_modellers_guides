# Setting up and using Windows WSL

Windows WSL is a virtual linux platform for windows. It enables you to run a linux machine from within your windows environment without the need for complicated setup or restarts.
Using a linux environment enables things like consistent software environments which makes sharing software builds much easier.

## Setup

Windows WSL is now much easier to setup and (In theory) just requires a single command. To see the latest setup instructions go here: https://docs.microsoft.com/en-us/windows/wsl/install

## Use

Once you have your WSL setup there are a number of use cases

To start your WSL environment go to the windows button and type `Ubuntu`. This should show you the Ubuntu app. Clicking on this should open a terminal.
From here you can run any linux command. To see some useful commands visit this link: https://towardsdatascience.com/16-must-know-bash-commands-for-data-scientists-d8263e990e0e

### Docker

Docker is a *containerized environment*. It works by packaging up everything that needs to be installed to run a program into a single file. This file can then be loaded up from any machine to ensure a consistent environment.

Setup instructions are here: https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-containers

It is recommended to also follow the visual studio code instructions here too.

### Visual Studio Code

If you also followed the visual studio code instructions above you should now have a file editor that is linked to your WSL environment.

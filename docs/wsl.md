---
hide:
  - navigation
---
# WSL
WSL stands for Windows Subsystem for Linux. It is a way to use Linux in Windows, like a Windows application.

## Install Ubuntu from Windows Store
You can [install Ubuntu from Windows Store](https://www.microsoft.com/store/productId/9MTTCL66CPXJ). There are multiple versions available from which you can choose one among them.

## Launching Ubuntu
1. After installing, open Ubuntu from Start Menu by searching for `Ubuntu`
2. When opened for the 1st time, it would prompt to set up root (administrator) user name and password. Kindly note that when typing your password, it would not show/display in the terminal but worry not, its being taken.
3. Ubuntu installed this way from Windows Store doesn't have a GUI and has only command line terminal. But it is possible to set up and use VS Code from the Ubuntu environment.

## Installing WSL Extension in VS Code
Open VS Code in your Windows OS and install [WSL extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ws) from Microsoft.


## Setting up Git in WSL
You can setup git inside the Ubuntu environment and code/develop from Ubuntu environment.

## Opening a Folder from Ubuntu in VS Code
1. Open Ubuntu application from start menu and you can navigate to the folder that you would like to open using `cd` commands. 
2. Once there, you can use `code .` command to open that folder in VS Code. The dot indicates to open the current directory in VS Code.

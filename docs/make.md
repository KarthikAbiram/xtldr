---
hide:
  - navigation
---

# Make
Setting up "make" in Windows involves two steps:

1. Installing make
2. Adding make directory to Environment Variable

## Install Make
Make can be installed using winget, an in-built Windows package manager.
```
winget install -e --id GnuWin32.Make
```
This will download and launch the GnuWin32 Make installer. Once installed GnuWin32 would be installed and available at below location:
```
C:\Program Files (x86)\GnuWin32\bin
```

## Add to Path
Even after installation is completed, make would not be detected in command prompt/power shell. This is because the directory containing the make.exe is not added to the "Path" environment variable.

1. Search for `Edit the system environment variable` in Windows search bar and open it.
2. This would open the `System Properties` dialog. Click on `Environment Variables...` option.
3. Here you can either add the path to either `User` or `System` environment variables - use System if you would like to add this path for all users.
4. Choose the `Path` variable and click `Edit`. Add the path using the `New` option as shown below.
![windows system properties](images\windows_system_properties.png){ : style="height:300px"} ![environment variables](images\environment_variables.png){ : style="height:300px"} ![edit environment variables](images\edit_environment_variable_path.png){ : style="height:300px"}
1. Click OK to close all the dialogs.

**Important thing to note:** You need to close and reopen any already open command terminals for make to be detected. You also need to close and reopen VS Code for the new path to be detected in the VS Code terminal.

## Verify Make Installation
Open a new command prompt or bash shell and provide below command to check if make is detected:
```
make --version
```
This is expected to give a response as below:
```
GNU Make 3.81
Copyright (C) 2006  Free Software Foundation, Inc.
This is free software; see the source for copying conditions.
There is NO warranty; not even for MERCHANTABILITY or FITNESS FOR A
PARTICULAR PURPOSE.

This program built for i386-pc-mingw32
```
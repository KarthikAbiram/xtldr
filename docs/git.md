---
hide:
  - navigation
---

# Git

## 🛠️ Install Git in Your PC
[Download](https://git-scm.com/downloads) and install git

## 🛠️ PC Setup

### Generate SSH Key

 1. Open Git Bash from Start Menu.
 2. Check if there are SSH keys already in your system under ".ssh" folder, using below command in git bash. The "-al" argument is for listing all files, with a separate line for each file name.
  `ls -al ~/.ssh`
 3. If you see that a SSH key has already been created for the account that you want, you can skip this section and move to the next section.
 4. If you got an error saying that the .ssh folder doesn't exist, create it using below command.
`mkdir .ssh`
 3. Switch to the .ssh folder.
`cd .ssh`
 4. Create a SSH key in your system using below command. This command uses "rsa" algorithm, uses 4096 bits and uses email address as comment. Replace the email address with your email address.
`ssh-keygen -t rsa -b 4096 -C youremail@example.com`
5. This would prompt for a file name. "id_rsa" would be the default file name. For using multiple accounts, its recommended to use an identifier along with the default name. Give a name that you can easily associate with the account. Eg: id_rsa_<git_username>
6. It would now prompt for a passphrase. Press enter twice if you would like to skip providing a passphrase.
7. These steps now would have created the public and private key in the ".ssh" folder. You can use "ls" command to list the files in the current directory and verify.
`ls`

### Add Your Private SSH Key to SSH Agent

(May be, below are not needed. Confirm)
1. Ensure that you are in ".ssh" folder by checking the present working directory command.
`pwd`
This would output something like
`/c/Users/<user_name>/.ssh`
2. If you are not yet in the .ssh folder, use change directory to go to the ".ssh" folder.
`cd .ssh`
3. Start SSH Agent using below command.
`eval "$(ssh-agent -s)"`
4. Add your SSH private key file, whose file name you had provided in the previous section. 
`ssh-add id_rsa_<git_username>`

### Add Your Public SSH Key to GitHub

 1. The ssh keys that you have created would be at `C:\Users\<user_name>\.ssh`
 2. Go to above location and open the *.pub file in a text editor, which is your public key. Copy the contents of above file. 
 3. Add your public SSH key to git settings. 
    1. For example, for github, it is [https://github.com/settings/keys](https://github.com/settings/keys). Click on **New SSH key**. 
    2. Give a name for your PC and paste the SSH key contents.

### Add Identity Keys to SSH Config File

If you had opted to save the file with a custom name other than "id_rsa", you need to add those file names to .ssh config file. The file needs to be created at below location without any extension:
`C:\Users\<user_name>\.ssh\config`
In this file, add below contents, one line for id_rsa file that you have created:
`IdentityFile ~/.ssh/id_rsa_git_username_1
IdentityFile ~/.ssh/id_rsa_git_username_2`

## Override User Name and Email for Each Repo

By default, git would use the global user name and email for all repositories. To view the global user name and email configuration, you can use the below command:
`git config --global -l`
If you would like to use a different user name or email for a particular repo, you can override it for each repository using below commands using git bash from your repository directory:
`git config --local user.name your_name
git config --local user.email your_name@domain.com`

## Sign your Commits

If you get `gpg: signing failed: No secret key
error: gpg failed to sign the data`, do the below steps:
-   List the secret keys available in GPG.
`gpg --list-secret-keys --keyid-format=long`
-   Copy your key and set using below command:
`git config --local user.signingkey your_key`
Use --global if you would like to apply this for systemwide.

## Contributing to Open Source Projects

1. Create a fork of the repo under your account
2. Clone the above fork in your PC
	3. git clone [url]
3. Create and checkout a new branch
	4. git checkout -b [your-new-branch-name]
4. Make changes and commit with your signature
	5. git commit -s -m [your commit message]
5. Push branch to your online repo
	5. git push -u origin [your-new-branch-name]
6. Create a pull request with your new branch

### 🧙 Tips

1. If you are in a conflicted state and want to go with "their" version:
git checkout --theirs .
git add .

## Multiple Git Profiles
To setup multiple git profiles in a system, refer to below links.
- [Git Conditional Configuration](https://stackoverflow.com/a/43884702)
- [Setup Case Insensitive Matching](https://stackoverflow.com/a/55107009)

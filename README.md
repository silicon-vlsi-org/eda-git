# About
Guides and resources to use `git` along with `gitHub` mostly in the context of using open-source EDA tools in Linux.

# Resources
- [Git Cheatsheet (PDF)](https://education.github.com/git-cheat-sheet-education.pdf)

# User Guides

## Frequently Used Functions
- `git clone <url>`
  - retrieve an entire repository from a hosted location via URL
- `git status`
  - show modified files in working directory, staged for your next commit
- `git pull`
  - fetch and merge any commits from the tracking remote branch
- `git add <file(s)>`
  - add a file as it looks now to your next commit (stage)
- `git commit -m “[descriptive message]” -a`
  - commit your staged content as a new commit snapshot
- `git push`
  - Transmit local branch commits to the remote repository branch

## Connect to GitHub repo using SSH 

- **Generate an SSH Key Pair**: In your WSL/Linux terminal, generate an *SSH key pair* using the following command:
  - `ssh-keygen -t rsa -b 4096`
- This will create two files: `id_rsa` (*private key*) and `id_rsa.pub` (*public key*).
- **Add the SSH Key to the SSH Agent**:
  - Start the SSH agent by running: `eval "$(ssh-agent -s)"`
  - Add your private key to the agent: `ssh-add ~/.ssh/id_rsa`
- **Add the Public Key to Your GitHub Account**:
  - Copy the content of your public key (id_rsa.pub): `cat ~/.ssh/id_rsa.pub`
  - Go to your `GitHub account Setting`s.
  - Navigate to the “**SSH and GPG keys**” section.
  - Click “**New SSH key**” and paste the copied key.
- Test the SSH Connection: Run the following command to test if your SSH key is working:
  - `ssh -T git@github.com`
  - You should see a message confirming your connection.
- **Clone a Repository** Using SSH:
  - Go to the GitHub repository you want to clone.
  - Click on the “**Code**” button and select the **SSH option**.
  - Copy the provided SSH URL.
  - In your WSL/Linux terminal, navigate to the directory where you want to clone the repository.
  - Run the following command, replacing <repository_url> with the actual SSH URL:
    - `git clone <repository_url>`

That’s it! You’re now set up to access GitHub repositories using SSH in WSL/Linux. For more detailed information, you can refer to the official GitHub documentation on connecting to GitHub with SSH1. 

- [Connecting to GitHub with SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)
- [How to Access Git Repo using SSH](https://askubuntu.com/questions/527551/how-to-access-a-git-repository-using-ssh)
- [Connect to GitHub with SSH](https://www.linuxfordevices.com/tutorials/linux/connect-to-github-with-ssh)
- [Git Clone with SSH](https://phoenixnap.com/kb/git-clone-ssh)


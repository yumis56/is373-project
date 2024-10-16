---
title: About Git and GitHub
---
# Git & GitHub
## What is Git?
Git is  Version Control System (VCS)

![Git Logo](/images/git-logo.png)

 - *However*, it handles information in a completely different from other VCSs, so you should see Git as a separated concept to avoid confusion
 - The main difference is that Git uses **Snapshot storage**, while other VCSs typically use **Delta storage**

#### Snapshot storage vs. Delta storage  
- **Snapshot storage**: Git stores data as a stream of snapshots.
  - Each snapshot represents the system state at a given time
  - Git will store unchanged files as a link to the previous identical files
  - More simple and efficient, but can consume a lot of storage
  
- **Delta storage** (delta-based version control): Other VCMs store data based only on file or system changes, rather than the entire state.
    - **Delta**: The difference between the current version and the previous version
    - All the **deltas** are combined to rebuild a system state
    - More complex, but can save on storage

Although delta storage is more storage-efficient, snapshot storage makes more sense for getting an accurate, updated representation.
- e.g. For banking, the account balance and banking statement would be a **snapshot**, while transaction history would be **delta storage**.

Now, back to Git:

 - Git generally works with your local files and resources; even if you have no internet or VPN access, you can still <code>commit</code> your changes to your local copy
   - Other VCMs may allow file edits, but do not allow "offline" database commits
 - Everything in Git is **checksummed**
  - All changes, incomplete transfers, and file corruptions are detected by Git
  - Git database stores everything by the **hash value** of its contents, not by file names
  - Git generally only <code>add</code> data, which improves data recovery by making it difficult to erase committed data


Git is the VCS, and GitHub is the one of many remote repository hosting sites.

***
## What is GitHub?
GitHub is a web-based service for hosting **remote repositories**

![GitHub Logo](/images/github-logo.png)

- You can use Git without GitHub, but GitHub needs Git to work

So, why bother using GitHub?
- Collaboration and Project Management: GitHub improves team collaboration with features like pull requests, code reviews, and issue tracking, as well as tracking commit histories to quantify individual contribution
- Access Control: You can choose the visibility and access rights of your code
- Documentation: GitHub Wikis and readme.md files are available as documentation tools  
- Remote repository backup: Even if your machine spontaneously combusts (or you lose your local directory in any way), as long as you have committed your local changes to the remote repository, you will be able to restore your files and directories from anywhere else!
- **CI/CD**: Continues Integration and Continuous Delivery. You can use **GitHub Actions** to automate your workflow to build, test, and deploy
- Portfolio / Networking: Remote repositories allow sharing of resources, contributions to public projects, and also allow you to showcase your projects and portfolio to peers and companies alike
- Web UI: GitHub has a user-friendly web interface, which is a helpful addition to command line controls

## The 3 Git workflow steps

![Git staging steps](/images/git-stages.png)

- **Working Directory**: The working directory, or working tree, is a <code>checkout</code> of a single version (branch) of a project. The files are pulled from a Git directory and placed on the local disk to be used or modified
- **Staging Area / Index**: The staging area stores the changes to be committed. It *only* prepares to commit changes that you have added for tracking
- **Repository / Git Directory**: After staging all the desired changes, the changes are then committed and then pushed to the Git Directory as a permanent snapshot


## Set Up Git and GitHub
### 1. [Download Git](https://git-scm.com/downloads)
  
### 2. Set a Git username
 - Open a terminal
 - to set the username for all repositories, use <code>git config --global user.name "Username Here"</code>
   - e.g.
   - <code>git config --global user.name "Jay Doe"</code>
   - <code>git config --global user.name "username123"</code>
   - To set for a single repository, simple exclude the --global tag
 - Typing <code>git config --global user.name</code> should return your username

### 3. Set a Git email
 - From terminal, type <code>git config --global user.email "your_email@here"</code>
   - Once again, exclude the --global tag to set email for only 1 repository
 - Typing <code>git config --global user.email</code> should return your email address
 - You will also add this email address to your GitHub account!

### 4. Set up a GitHub account
 - [Sign up for GitHub](https://github.com/) and follow the prompts
 - Verify your email address to access the neccessary features

### 5. Generate an SSH
  - From your terminal, type <code>ssh-keygen -t ed25519 -C "your_email@example.com"</code> with the email you use for GitHub
    - If the Ed25519 algorithm is not supported, you can use <code>ssh-keygen -t rsa -b 4096 -C "your_email@example.com"</code>
  - Press enter to accept the default location. If you already have an SSH key with an identical name, we reccomend choosing a custom name for your key, to avoid overwriting any existing keys
    - You can choose a passphrase or simply press enter to skip adding a passphrase

### 6. Add SSH Key to GitHub
 - From terminal, type <code>cat ~/.ssh/your_sshkey_name_here.pub</code> with the file path of your public key file
  - PLEASE MAKE SURE it ends with .pub, otherwise you may expose your private SSH key !!
 - Copy the displayed file contents
  - You can also open the .pub file in any text editor to copy the contents directly
 - On GitHub, access your **Settings**
 - Under **Access** section of the sidebar, click **SSH and GPG keys**
 - Click **New SSH key** or **Add SSH key**
 - Paste your key into the "Key" file
 - Give your key an identifiable nickname, e.g. the name of your class





***

## Other Resources

https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F

https://blog.git-init.com/snapshot-vs-delta-storage/

https://docs.github.com/en/actions/about-github-actions/understanding-github-actions

https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

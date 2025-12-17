## Using Git to Track and Manage Changes for a Simple Form

**Name:** Essence-Git  
**Lab:** Git Hands-on Lab  
**Repository:** simple-form  
**Tool Used:** Git Bash (Windows)



## Introduction

This document explains, step by step, how I carried out the Git hands-on lab to track and manage changes for a simple HTML form. The lab demonstrates cloning a repository, committing changes, pushing to GitHub, reverting files, branching, merging, and undoing unwanted changes.

Screenshots are included at each stage to provide evidence of the commands executed.

## Step 0: Creating the Project Files in VS Code

Before using Git, I first created the project files locally using Visual Studio Code.

I opened VS Code and created a new folder named `simple-form`. Inside this folder, I created two files: `form.html` and `style.css`.

![alt text](<git screenshot/form html.png>)

In `form.html`, I created a basic HTML form that collects the user’s name, email address, and message.  
In `style.css`, I added basic styling such as font styles, spacing, and layout to improve the appearance of the form.

I saved both files to ensure they were ready to be tracked using Git.

Also,Before working with Git locally, I created an empty repository on GitHub.

I logged into my GitHub account, clicked on “New Repository”, named the repository `simple-form`, and left it empty without adding a README or `.gitignore` file.

This repository was later connected to my local project folder

![alt text](<git screenshot/new  simple form repo.png>)


## Step 1: Clone the GitHub Repository

I cloned the existing empty GitHub repository named `simple-form` to my local machine and navigated into the repository directory.

```bash
cd ~/Documents
git clone https://github.com/essence-git/simple-form.git
cd simple-form
git status
```
 ![alt text](<git screenshot/screenshot 1.png>)

## Step 2: Add the HTML and CSS Files

I copied the `form.html` and `style.css`  files into the `simple-form` folder and confirmed their presence.


```bash
ls -al
```


![alt text](<git screenshot/Screenshot 2.png>)


## Step 3: Initialize Git and Connect to GitHub

Because the files were located inside a OneDrive directory, I initialized Git in the folder and linked it to my GitHub repository.

```bash
git init
git remote add origin https://github.com/essence-git/simple-form.git
git remote -v
```

![alt text](<git screenshot/Screenshot 3.png>)

![alt text](<git screenshot/Screenshot 4.png>)
## Step 4: Commit the Initial Version

I staged and committed the initial version of the HTML form and CSS file.

```bash
git add form.html style.css
git commit -m "Initial commit for simple form"
```


![alt text](<git screenshot/Screenshot 5.png>)

## Step 5: Push to GitHub

I renamed the default branch to `main` and pushed the initial commit to GitHub.

```bash
git branch -M main
git push -u origin main
```

![alt text](<git screenshot/Screenshot 6.png>)

## Step 6: Make and Track Changes

I modified `form.html` to include a phone number field and updated the styling in `style.css` by changing the font from Ariel to calibri . I then staged, committed, and pushed the changes.

  ![alt text](<git screenshot/change 1.png>)

  ![alt text](<git screenshot/change 2.png>)

```bash
git add form.html style.css
git commit -m "Added phone number field and updated styles"
git push origin main
```

![alt text](<git screenshot/Screenshot 7.png>)

## Step 7: View Project History

I viewed the commit history to review all changes made to the project.

```bash
git log
```

![alt text](<git screenshot/Screenshot 8.png>)

## Step 8: Revert to a Previous Version

After identifying the last working commit, I reverted only the `form.html` file to that version.

```bash
git checkout 7b44ba65178444e20000293896591f2dc18bc3a6 -- form.html
git add form.html
git commit -m "Reverted form.html to last working version"
```
![alt text](<git screenshot/Screenshot 9.png>)

## Step 9: Create a Branch for a New Feature

To experiment with a CAPTCHA feature, I created and switched to a new branch.

```bash
git checkout -b feature-add-captcha
```

![alt text](<git screenshot/Screenshot 10.png>)

## Step 10: Add CAPTCHA Feature

I edited `form.html` to add a CAPTCHA placeholder, then staged and committed the changes.

![alt text](<git screenshot/change 3.png>)

```bash
git add form.html
git commit -m "Added CAPTCHA feature"
```

![alt text](<git screenshot/Screenshot 11.png>)

## Step 11: Merge CAPTCHA Feature into Main

I switched back to the main branch and merged the feature branch, then pushed the changes to GitHub.

```bash
git checkout main
git merge feature-add-captcha
git push origin main
```

![alt text](<git screenshot/Screenshot 12.png>)
## Step 12: Undo Unwanted Local Changes

I discarded unwanted local changes made to `style.css` before committing.

```bash
git checkout -- style.css
git status
```

![alt text](<git screenshot/Screenshot 13.png>)

## Conclusion

Through this lab, I successfully demonstrated how to use Git to manage versions of a project, track changes using commits, revert files safely, work with branches, merge features, and synchronize a local repository with GitHub.

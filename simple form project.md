# Using Git to Track and Manage Changes for a Simple Form

___

Before starting, i ensured:

1. Git was installed on my machine
2. To have basic understanding of Git commands
3. An existing GitHub repository of simple-form-project
4. A simple HTML form (form.html) and CSS file (style.css) in a local directory, which collects user information such as name, email, and message

___

**TASK:**

The following were the task to be carried out in this project

1. Clone the GitHub Repository
2. Stage the Form File
3. Commit Your Initial Version
4. Push to GitHub
5. Make and Track Changes
6. Push Changes to GitHub
7. View the Project’s History
8. Revert to a Previous Version
9. Branching for New Features
10. Push Merged Changes to GitHub
11. Undoing Local Changes
12. Pulling Updates from GitHub

___

## 1. Clone the GitHub Repository

___

**Objective:**

To clone an existing GitHub repository called simple-form to my local machine(Host machine)
___

**Procedure:**

Cloning a repository is like making a copy of a book from the library so you can read and make notes at home without touching the original.

The steps I followed are as follows:

- I opened GitHub in my browser & navigated to the repository (simple-form) I wanted to work on.
- I clicked the **Code** button & copied the URL for **HTTPS** (NB: any of the provided URL can be used).
- I opened Git Bash in Visual Studio Code (my preferred terminal window) where I wanted to save the repository.
- I ensured my current working directory was set to the folder **Workspace**
- With my Git bash terminal window opened, i Run the clone command

```powershell
git clone <repository-URL>
```

- I replaced `<repository-URL>` with the URL I copied from GitHub which turn out to be

```powershell
git clone https://github.com/yourusername/simple-form.git

```

- I executed the command `cd simple-form` to enter into the folder to start working

___

**Outcome:**

I now have a full copy of the repository on my local machine and can start working on the project safely.
___

## 2. Stage the Form File

___

**Objective:**

To stage an HTML file (form.html) and CSS file (style.css) in the simple form repositiory in my local cloned repository.
___

**Method:**

Staging a file in Git means preparing it to be included in the next commit. In simple terms: staging is like putting your work into a “ready to save” box before officially saving it in Git history.

Below are the steps I took:

- I ensured I was inside the cloned repository folder (simple-form) by executing the command `cd simple-form`
- I checked the status of the repository to see untracked files with the command `git status`. No files was tracked, so i proceeded with the next step
- I placed the HTML form file (form.html) and CSS file (style.css) in this simple form folder
- On the command line, i used Git to add the HTML form file (form.html) and CSS file (style.css) to the staging area with the command

```poweshell
git add form.html style.css
```

- I verified that the files were staged with the command

```powershell
git status
```

___

**Outcome:**

The HTML form and CSS files were successfully staged, meaning they are ready to be committed to the repository.

___

## 3. Commit Your Initial Version

___

**Objective:**

To commit initial simple-form after few changes made as a result of HTML and CSS file staged.

___

**Procedure:**

In Git, “commit a file” means i am saving a snapshot of my changes in my local repository.

I completed the process using the following steps:

- After staging the files (form.html and style.css), I committed them to the repository with a descriptive message by executing the command:

```powershell
git commit -m "Initial commit for simple form"
```

- I verified the commit by checking the status with the command:

```powershell
git status
```

- The terminal confirmed there were no changes to commit for me.

___

**Outcome:**

I successfully committed the initial version of the project. All staged files are now recorded in the Git history, allowing me to track changes and revert if necessary.

___

## 4. Push to GitHub

___

**Objective:**

To push the initial commit to the remote repository

___

**Procedure:**

I followed the steps outlined below:

- I ensured I was in the repository folder (simple-form) on my local machine
- I linked the local repository to the remote GitHub repository (if not done already) by executing the command

```powershell
git remote add origin https://github.com/yourusername/simple-form.git
```

- I pushed the committed changes to the remote repository using the command

```powershell
git push origin main
```

- I verified on GitHub that the files (form.html and style.css) appeared in the repository.

___

**Result:**

The initial commit was successfully pushed to GitHub. The project is now safely stored in the cloud and can be accessed or collaborated on by others.
___

## 5.  Make and Track Changes

___

**Objective:**

To modify form.html to include an additional field for a phone number and update the styling in style.css. After making these changes, stage and commit the updated files with a message.

___

**Method:**

Below are the steps I took:

- I opened form.html in Visual Studio Code and added a new input field for the phone number.
- likewise for style.css, i opened it and added a new styling as required
- I saved both form.html and style.css new modification on my local computer
- While in my simple-form directory, I staged and committed the changes made to form.html and style.css.

```powershell
# To stage the changes 
git add form.html style.css

# To commit changes
git commit -m "Added phone number field and updated styles"
```

**Result:**

The HTML form now includes a phone number field. The form’s appearance is updated and more user-friendly.
___

## 6.  Push Changes to GitHub

___

**Objective:**

To Push the latest changes for the form file (HTLM & CSS file) to the remote repository 
___

**Method:**

- While in the simple-form directory, i run the command

```powershell
git push origin main
```

___

**Result:**

The modification was successfully pushed to GitHub repository. The project is now safely stored in the cloud and can be accessed or collaborated on by others.

___

## 7. View the Project’s History

___

**Objective:**

To check the Git history and review all modifications in the simple-form repository.

___

**Procedure:**

- While in the simple-form repository folder, I ran the command below to view the Git log, which displays the recent changes.

```powershell
git log
```

___

**Result:**

I can now see all the changes made to the project over time, including who made each change, when it was made, and why. This makes it easier to track progress, revert changes if needed, and understand the project’s evolution.
___

## 8. Revert to a Previous Version

___

**Objective:**

To restore form.html to its last known working state in the repository in order to fix the bug introduced by a previous change, without affecting other files.

___

**Procedure:**

I followed the steps outlined below:

- While in the simple-form repository folder, i run the command below to check the log by finding the last commit hash of the last working version

```powershell
git log
```

- I noted and copied the previous commit ID of the version I wanted to go back to.
- i run the command below to revert back to the previous commit

```powershell
git checkout  d4dcff33d6876c34a63c1446906401e7e5e7050e -- form.html
```

___

**Outcome:**
I successfully restored the simple-form project to a previous stable version. Hence, the repository remains stable and safe for further development. Also, mistakes or unwanted changes were undone without losing the overall history
___

## 9.  Branching for New Features

___

**Objectives:**

1. To create an isolated branch (feature-add-captcha) so i can safely develop and test the CAPTCHA feature without affecting the main branch and then switch to it.
2. To make the necessary changes for the CAPTCHA feature, then stage and commit them
3. To merge the changes back into the main branch

___

**Procedure:**

Creating a branch allows you to work independently either locally or on GitHub without affecting or risking changes to the original main files. Here, I am creating a new branch from my current working branch

I followed the steps outlined below:

- I run the command below to create a new called feature-add-captcha

```powershell
git checkout -b feature-add-captcha
```

- While in my new feature-add-captcha branch, I opened form.html and i added a and saved it.
- While in my simple-form directory, I staged and committed the changes made to form.html by executing the command below

```powershell
# To stage the changes 
git add form.html

# To commit changes
git commit -m "Added CAPTCHA feature"
```

- To merge the changes back into my main branch by executing the command below first switch to my main branch where my merge will be carried out

```powershell
git checkout main
```

- I run the command below while in my main branch to merge the new feature-add-captcha branch created

```powershell
git merge feature-add-captcha
```

___

**Result:**

I successfully implemented the CAPTCHA feature in the feature branch. All changes were safely staged and committed. The feature-add-captcha is now ready for testing or merging into the main branch.
___

## 10. Push Merged Changes to GitHub

___

**Objective:**

To push the merged changes to github after successful merge of the new feature-add-captcha into the main branch

___

**Procedure:**

- I run the command below to push the changes to Github repository

```powershell
git push origin main
```

___

**Outcome:**

I have successfully push the merged main file from the feature-add-captcha branch to the Github repository

___

## 11. Undoing Local Changes

___

**Objective:**

To discard uncommitted local changes in style.css and restore the file to its last committed state in the repository.

___

**Steps:**

I followed the steps outlined below:

- I opened my CSS (style.css ) file and made some unwanted changed to the already drafted code
- I run the code below to stage the edited style.css file

```powershell
git add style.css
```

- Finally, i discard the unwanted local changes and restore my last committed version for the style.css file with the command

```powershell
git checkout -- style.css
```

- My working directory was clean, confirming the file was restored

___

## 12. Pulling Updates from GitHub

___

**Objective:**

To update my local repository with the latest changes from the remote GitHub repository, ensuring my local copy stays in sync with others’ work.

___

**Steps:**

I followed the steps outlined below:

- Navigating to Github website, i selected my simple-form repository from the list of available repository, i add a file named **register.html** with some content inside and selected **commit changes**
- i added a commit message **Add a register.html file** and select **commit changes** again to finally save the register file created
- I ensured to be in simple-form directory in my git bash terminal so as to perfectly pull the changes down to my local repository
- Lastly, i run the below to pull the changes down to my local repository

 ```powershell
git pull
```

- My local repository was updated with the latest changes from GitHub

___

**Outcome:**

By completing these tasks, you will learn how to:

- Clone an existing GitHub repository to your local machine.
- Track changes using commits.
- Push and pull changes to and from GitHub.
- Revert files to previous versions in case of errors.
- Manage different features with branching.
- Undo unwanted changes before committing.

___

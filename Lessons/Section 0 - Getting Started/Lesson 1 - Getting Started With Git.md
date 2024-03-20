---
tags:
  - Lesson
aliases:
  - GitHub
---
- Explain what version control is for and why its useful
- Write a tutorial on how to create a repo on github


- Install [Git Bash](https://git-scm.com/download/win)
	- Get the 64-bit standalone installer
	- Install using all the default values
		- Make sure you install the Git Credential Manager 
- Find your visual studio project folder
	- copy the address
		- matt had issues with backslashes in the cd command
- Initialize the git repo
	- Matt had issues where github was breaking because visual studio was running in his project
- Make them download the .gitignore
	- Make them rename it to `.gitignore`
	- add it to source control


# Using GitHub

Before beginning this section, please go to [GitHub](https://github.com/) and sign in, or create an account.

## Create a Personal Access Token (PAT)

https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-fine-grained-personal-access-token

Profile Photo -> Settings -> Developer Settings -> Personal Access Tokens -> Tokens (Classic)

- Set Expiration to 'No Expiration' to not have to deal with this again
- Click the 'Repo' checkbox to give your token access to manage repos
- Click 'Generate Token' at the bottom of the page
- Copy your new token and save it somewhere you won't lose it. This is the only time GitHub will ever send the token to you, so you'll need to store it permanently.

## Uploading Your Repository to GitHub

```shell
git init
```

Stage all of your changes

```shell
git add .
```

Create the commit

```shell
git commit -m "Initial commit"
```

https://docs.github.com/en/migrations/importing-source-code/using-the-command-line-to-import-source-code/adding-locally-hosted-code-to-github#adding-a-local-repository-to-github-using-git
- make a repo
	- private repo
	- set the repo name to whatever you want
	- make sure it's empty, or you won't be able to upload your code
		- do not add a readme file
		- do not add a .gitignore
		- do not add a license
	- click 'create repo'
	- copy the https value

Push your changes to GitHub

```shell
git push
```

it'll annoy you about not having the upstream set. run this command
```shell
git push --set-upstream origin master
```

Add the 'origin' remote using your github account

```shell
git remote add origin REMOTE-URL
```

Now run the below command to check if you set up the 'origin' remote correctly:

```shell
git remote -v
```

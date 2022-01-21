* In this homework, you are going to send `basiccalculator.py` from your local to the remote by using the following Git commands.

* Source of the basiccalculator.py is [here](https://gist.github.com/complxalgorithm/ee685852a2a37e88ebc8d64d2d126d91).

### 1. Initialize the Working Directory

* To send a file from local to remote, first of all you need to initialize your working directory. Namely, you should create your working directory. Use the required command and initialize your working directory.

```bash
git init
```


### 2. Sending the file to Staging Area

* As you remember, we have 3 different workspaces in GitHub: Working Directory, Staging Area and Commit Store. Now, it is time to send `basiccalculator.py` to the Staging Area. Use the required command and send `basiccalculator.py` to the Staging Area.

**Note:** You can complete this step with 2 different commands. Both of them are applicable.

```bash
git add .

# or
git add basiccalculator.py
```

### 3. Checking the Status

* Now let`s check the status of the Git. Use the required command and check the status of Git. 

**Note:** The command you need to use is used for checking the status of Working Directory and Staging Area. It doesn`t use to check the status of Commit Store. Check your slides for more info.

```bash
git status
```

### 4. Commiting the File

* Commit the `basiccalculator.py` with following note: "This is the commit of my homework."

```bash
git commit -m "This is the commit of my homework."
```

### 5. Add Origin to Remote

* Add Origin to remote by using the required command. For that, create a new repository from GitHub Website; name it as your wish and use this repository`s URL.

```bash
git remote add origin [REMOTE_URL]
```

### 6. Pushing Data to Remote 

* Final step for your homework; complete the push by pushing `basiccalculator.py` with the required command.

```bash
git push --set-upstream origin master

```
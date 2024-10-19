### 1. **Navigate to Your Project Folder**

Open a terminal (or command line) and navigate to the folder where your GitHub project (website) is located.

bash


`cd /path/to/your/project`

### 2. **Check the Current Status**

Run the following command to check what changes you have made:


`git status`

This will list any modified files or new files that haven't been added to a commit yet.

### 3. **Add Your Changes**

If you want to commit all the changes, use:

`git add .`

If you only want to add specific files, replace `.` with the file names:

`git add filename1 filename2`

### 4. **Commit the Changes**

After adding the files, commit the changes with a message describing what you have done:

`git commit -m "Your commit message here"`

Make sure the commit message is meaningful, like `"Updated the homepage layout"`.

### 5. **Push the Changes**

Push your commit to GitHub using:

`git push origin main`

If you're using a branch other than `main`, replace `main` with the name of your branch.

### 6. **Check on GitHub**

After pushing, you can go to your GitHub repository and see the changes reflected.
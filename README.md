### Create a Jenkins job to execute a SQL script when a new commit is made

Step 1. Initialize a Git repository in a current directory:
```
git init
```
Step 2. Go to ```./.git/hooks``` and create a file named ```post-commit```.  
Step 3. Add the following content to the file to make Git trigger a Jenkins job associated with this repository:
```
#!/bin/sh
curl http://localhost:8080/git/notifyCommit?url=file://<absolute-path-to-repository>
```
Step 4. Make this file executable with ```chmod u+x post-commit```.  
Step 5. Create a Jenking job with the following settings:  
**Job type**: pipeline  
**Build Triggers**: Poll SCM  
**Pipeline**:  
&nbsp;&nbsp;Definition: Pipeline script from SCM  
&nbsp;&nbsp;SCM: Git  
&nbsp;&nbsp;Repository URL: ```file://<absolute-path-to-repository>```
&nbsp;&nbsp;Script path: Jenkinsfile  
&nbsp;&nbsp;Lightweight checkout: deactivate  
Step 6. Create a Jenkinsfile and add place it into a root of the repo.  

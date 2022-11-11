Go to ./.git/hooks and create a filae named ```post-commit```.
Make this file executable with ```chmod u+x post-commit```.
Add the following content that will trigger a Jenkins job associated with this repository:
```
#!/bin/sh
curl http://localhost:8080/git/notifyCommit?url=file:///home/ed/Dev/sf-jenkins-homework
```


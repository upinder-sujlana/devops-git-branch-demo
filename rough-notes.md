```
[+] First I went to github.com and created a new repo . 
    This automatically creates "master" branch (or atleast make it default)
[+] Then I am going to push a dummy file to the master branch:
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo$ ls
unpacking_ucsm.sh
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo$
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo$ git init
Initialized empty Git repository in /mnt/c/Users/usujlana/Desktop/TFTP/devops-git-branch-demo/.git/
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo$ git add *
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo$ git config --global user.email "upigrad@gmail.com"
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo$ git config --global user.name "upinder-sujlana"
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo$ echo "# First push to the master branch" >> README.md
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo$ git commit -m "First Commit"
[master (root-commit) 19d6637] First Commit
 1 file changed, 39 insertions(+)
 create mode 100644 unpacking_ucsm.sh
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo$ git remote add origin https://github.com/upinder-sujlana/devops-git-branch-demo.git
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo$ git push -u origin master
Username for 'https://github.com': upigrad@gmail.com
Password for 'https://upigrad@gmail.com@github.com':
Counting objects: 3, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 793 bytes | 793.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
remote:
remote: Create a pull request for 'master' on GitHub by visiting:
remote:      https://github.com/upinder-sujlana/devops-git-branch-demo/pull/new/master
remote:
To https://github.com/upinder-sujlana/devops-git-branch-demo.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo$

[+] Now I went to github and confirmed the files are there.
[+] Now going to github and creating a developer1 branch. Basically github > Code > click branch and type develoer1 to create the
    branch
[+] After that I did:
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo$ git clone -b developer1 https://github.com/upinder-sujlana/devops-git-branch-demo.git
Cloning into 'devops-git-branch-demo'...
remote: Enumerating objects: 6, done.
remote: Counting objects: 100% (6/6), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 6 (delta 0), reused 3 (delta 0), pack-reused 0
Unpacking objects: 100% (6/6), done.
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo$ ls
README.md  devops-git-branch-demo  unpacking_ucsm.sh
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo$ ls -lrt
total 4
-rwxrwxrwx 1 cisco cisco 1052 Nov  3 12:48 unpacking_ucsm.sh
-rwxrwxrwx 1 cisco cisco   34 Nov  3 12:53 README.md
drwxrwxrwx 1 cisco cisco 4096 Nov  3 13:04 devops-git-branch-demo
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo$

[+] Notice a new directory devops-git-branch-demo got created. cd into it
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$ ls
unpacking_ucsm.sh
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$

[+] Adding a line to the file to modify it from file in master:
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$ echo "#This is just a test comment string" >> unpacking_ucsm.sh
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$ tail unpacking_ucsm.sh
do
 dir="${file%.tar.gz}"
 mkdir -- "$dir"
 cp -- "$file" "$dir"
 cd "$dir"
 tar -xzf *.tar.gz --checkpoint=.3000;echo
 rm -rf *.tar.gz
 cd ..
done
#This is just a test comment string
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$

[+] Also going to create a test file:
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$ touch simplefile.txt
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$ echo "simple file for testing" > simplefile.txt
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$

cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$ ls -lrt
total 4
-rwxrwxrwx 1 cisco cisco 1088 Nov  3 13:06 unpacking_ucsm.sh
-rwxrwxrwx 1 cisco cisco   24 Nov  3 13:09 simplefile.txt
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$

[+] So which branch does git think I am on currently?
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$ git branch
* developer1
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$

[+] lets add the modified + newly created file:-
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$ git add .
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$ git commit -m "First commit to developer1 branch"
[developer1 804843f] First commit to developer1 branch
 2 files changed, 2 insertions(+)
 create mode 100644 simplefile.txt
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$ git log --oneline
804843f (HEAD -> developer1) First commit to developer1 branch
19d6637 (origin/master, origin/developer1, origin/HEAD) First Commit
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$

[+] Now Push the files over to github:
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$ git push -u origin developer1
Username for 'https://github.com': upigrad@gmail.com
Password for 'https://upigrad@gmail.com@github.com':
Counting objects: 4, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 397 bytes | 397.00 KiB/s, done.
Total 4 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/upinder-sujlana/devops-git-branch-demo.git
   19d6637..804843f  developer1 -> developer1
Branch 'developer1' set up to track remote branch 'developer1' from 'origin'.
cisco@USUJLANA-41PCQ:~/Desktop/TFTP/devops-git-branch-demo/devops-git-branch-demo$

[+] After this I went to github and saw the modified unpacking_ucsm.sh file and also the simplefile.txt file  :
https://github.com/upinder-sujlana/devops-git-branch-demo/tree/developer1

[+] After above I checked the master branch and the original files are still intact:
https://github.com/upinder-sujlana/devops-git-branch-demo/tree/master

[+] To play between branches locally & remote you can use below guide:
https://www.nobledesktop.com/learn/git/git-branches

[+] 

```

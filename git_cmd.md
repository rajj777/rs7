**Delete the file**

&#x09;**Linux/macOS: \~/.git-credentials**

&#x09;**Windows: C:\\Users\\<YourUsername>\\.git-credentials**
rm \~/.git-credentials

git config --global --unset credential.helper

\-----------------------------------------------

**-> Store credentials permanently (HTTPS method)**

git config --global credential.helper store
------------------------------------------------


**Scenario 1: Local project → New GitHub repo**

git init

git add .

git commit -m "Initial commit"

git remote add origin https://github.com/YourUsername/YourRepo.git

git branch -M main

git push -u origin main

\-----------------------------------------------------



**Scenario 2: GitHub repo first → Clone → Write code**

git clone https://github.com/YourUsername/YourRepo.git

cd YourRepo

git add .

git commit -m "Initial commit"

git push -u origin main

\--------------------------------------------------------



**you want to explore Git history and roll back to a specific commit.** 

mkdir myproject

cd myproject

git init



echo "First version" > file.txt

git add file.txt

git commit -m "Commit a: initial version"



echo "Second version" >> file.txt

git add file.txt

git commit -m "Commit b: added second version"



echo "Third version" >> file.txt

git add file.txt

git commit -m "Commit c: added third version"



git log --oneline



git revert <commit\_hash>



\-------------------------------------------------

**# Full Git branch merge workflow demo**



mkdir branch\_demo

cd branch\_demo

git init



echo "Base version" > file.txt

git add file.txt

git commit -m "Initial commit on main"



git checkout -b a

echo "Changes from branch A" >> file.txt

git add file.txt

git commit -m "Commit on branch A"



git checkout main



git checkout -b b

echo "Changes from branch B" >> file.txt

git add file.txt

git commit -m "Commit on branch B"



git checkout main



git merge a -m "Merging branch A into main"



git merge b -m "Merging branch B into main"



git log --oneline --graph --all




























































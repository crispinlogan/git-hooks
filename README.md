# git hooks


## commit-msg
### Info
This repo currently contains just one git hook - commit-msg, which checks that your commit message obeys 5 of the 7 rules of the 7 rules for commit messages (all except rules 5 and 7).

1. Separate subject from body with a blank line
2. Limit the subject line to 50 characters
3. Capitalize the subject line
4. Do not end the subject line with a period
5. Use the imperative mood in the subject line
6. Wrap the body at 72 characters
7. Use the body to explain what and why vs. how

I found this [repo](https://github.com/kiecodes/git-hooks)  useful in creating the repo here, which is a simplified version.

## "Install"
To "install" the commit-msg git hook, you can either clone this repo, run `bash install-commit-msg.sh` in the root of the cloned repo and then change the name of the repo and delete the .git file and any other remaining files to start a repo from scratch, OR if you have an existing repo you want to add this git-hook to, then download the commit-msg file, place it in `.git/hooks/` and ensure it is executable by running `chmod +x .git/hooks/commit-msg` (this is basically what is done in the install-commit-msg.sh file).

## Test install
You can now run
```
echo "testing" >> test.txt
git add test.txt
git commit -m "This is a commit message that is longer than the 50 character rule for the subject line"
```
and the commit-msg hook should prohibit that commit being allowed as it violates rule 2.
# Learn <!-- Git -->
![](https://git-scm.com/images/logos/downloads/Git-Logo-2Color.png) <!-- .element: style="border: 0; background: white" -->

---
## Housekeeping
:: First some housekeeping
||
Session is for you

(should be interactive) <!-- .element: class="fragment" -->
||
Lots of demos

(yay!) <!-- .element: class="fragment" -->

---
## Why Learn Git
||

Know the tools of your trade
::
As Professional programmers, we should know how to use our tools
* Carpenter knows his/her tools
* Chef knows his/her tools

||
Git is de-facto standard

(Unique in the Software Development world) <!-- .element: class="fragment" -->
::
* Git is pretty much the standard now
* Unlike other Software Development tools
  * Ent Languages (Java, .NET)
  * UI Frameworks (Angular, React, Vue)
  * Java IDE (Eclipse, IntelliJ)
  * Of course - text editors
* Being de-facto standard makes more valuable
||
Be more productive!

---
## Git Bash
* Demos will use git bash <!-- .element: class="fragment" -->
* Recommendation: use git bash while learning <!-- .element: class="fragment" -->
::
Tools like SourceTree are handy but only if you understand what they are doing for you.

Otherwise, great way to get yourself in trouble

Recommend using git bash for 3 months before using other tools

---
## About Git
||
Git is different from most other SCMs
::
Git is not like SVN
||
Git is distributed

<span class="fragment fade-up fade-in">
	<span class="fragment fade-up fade-out">ok?</span>
</span>
::
That's great!  what does it mean?
* Every repo is a complete copy
  * Why command called "clone"
* Server not needed for most commands
* To start we will ignore server and do everything local!
||
# Demo
::
* Create new repo
* Create initial commit
||
### Summary
* Git is distributed - can work without server

---
## Commits
<div class="fragment">
A commit (noun) is:
  <ul>
  <li> A version of the files tracked in git
  <li> Unique ID (SHA-1)
  <li> Author and timestamp of changes
  <li> A message/description
  <li> pointer to parent commit(s)
  </ul>
<div>
<div class="fragment">
To commit (verb):<br/>
  <ul>
  <li> The action of creating a commit
  </ul>
<div>

||
# Demo
::
* Create several commits
* Use git log to show the history
* Each commit has pointer to parent

---
## Branching
||
Branches are just pointers to commits
||
Branches are just pointers to commits
::
Branching is cheap (unlike other SCMs)
||
# Demo
::
* Create some branches and commits
* Use git log to show the branches
||
HEAD
::
Pointer to the checked out branch
||
### commit-ish

Something that can refer to a commit <!-- .element: class="fragment" -->
||
### commit-ish Examples:  <!-- .element: class="fragment" -->
* Commit ID: 94d98ff7d89e35c7d5b289ba387cdb0d42b30794  <!-- .element: class="fragment" -->
* Short Commit ID: 94d98f  <!-- .element: class="fragment" -->
* Branch Name: my-branch  <!-- .element: class="fragment" -->
* Current branch: HEAD  <!-- .element: class="fragment" -->
* commit ancestor (with \~): 94d98f~2  <!-- .element: class="fragment" -->
* commit parent (with ^): 94d98f^2  <!-- .element: class="fragment" -->
* Remote Branch  <!-- .element: class="fragment" -->
* Tag  <!-- .element: class="fragment" -->
::
many commands accept a commitish


||
Deleting Branches
::
Deleting branches does not delete history!  just the pointer

However, if commit is not part of any branch, it is "effectively" deleted

Not really - reflog maintains recent history

---
## Merge
||
Merge history of 2 branches
||
# Demo
::
* non-conflict example
* Merges have 2 parents
* merge conflict example
* Can follow renames
* diff3
* Never make code changes when resolving merge conflicts - only resolve conflicts!
||
### Summary
* Merges have 2 parents (all commit history is included)
* Git does good job merging changes
* Merge conflicts typically occur when both branch changes the same line(s)
* diff3 is awesome
```bash
git config --global merge.conflictstyle diff3
```

---
## Changing History
||
# Disclaimer
## Never change history other work is based on
::
Do not change history of a commit
* that other work is based on
* has been merged into master/develop

Cause complication if not used carefully, but great tools if used responsibly

Like a saw - this is a great tool, but be careful to not cut off your fingers!
||
## Amend Commit
::
* Edit the most recent commit
* Add or remove changes, edit commit message
||
# Demo
::
* Example of Amend Commit
||
## Rebase
::
Rebase rewrites the commits as if branched from another point
||
# Demo
::
* Show a rebase
* Treats each commit as a patch, applys patch to new branch
* Can have merge conflicts!
* Maintains author date and timestamp
||
## Rebase Interactive
::
Allows editing of rebase
||
# Demo
||
## Cherry-Pick
::
Apply a commit to your current branch

Treats it as a patch, maintains author and timestamp
||
# Demo
::
* Show a cherry pick

* Explain: note that a rebase is really just a series of cherry-picks
||
## Summary
* Helpful Tools
* Use carefully
::
* Helpful tools
  - to keep your commit history clean, tell a story
  - Add productivity (can commit frequently, clean up later)
  - Makes TDD more effective
* Use carefully

---
## Working With Remote Repos
||
## Remotes
::
Demo: what remote settings look like

Clone - automatically sets up remote called origin

Can add remotes
||
## Remote Branches
::
Branches that match the branches on a remote

show examples

format: remote/branchname

Cannot checkout directly or modify
||
## Fetch
::
Fetch updates all the remote branches

Demo a fetch
||
## Pull

(fetch, then merge) <!-- .element: class="fragment" -->
::
Is really just doing a fetch, then merge

Can do these commands individually (my preference, as it provides me more control)
||
## Push
::
Push your changes to a branch on remote

Local branch name does not have to match remote branch name (though this does make it easier)

Demo
||
## Pull Request

(Think "Merge Request") <!-- .element: class="fragment" -->
::
Pull Request name comes from how to work on Open Source Projects
  - cannot edit actual source
  - Must fork, make changes, then request changes from your fork are pulled in

Just pretend it is called a "Merge Request"
||
## Tracking branches
::
Used to show number
- commits on local not on remote (ahead)
- commits on remote not on local (behind)

Remember - can only be updated when remote is fetched

---
# Tags
::
Nutshell: Tags are like branches (pointer to commit) but does not change

Used for releases

No need to demo, just understand what they are
---
# My Favorite Resources
<div class="fragment">Git Book: <a href="https://git-scm.com/book/en/v2">https://git-scm.com/book/en/v2</a> (Ch 1,2,3,5)</div>

<div class="fragment">Good Commit Messages: <a href="https://chris.beams.io/posts/git-commit/">https://chris.beams.io/posts/git-commit/</a></div>
::
Git Book: Written by maintainers of git, open source, available as webpage or ebook

---
# Q & A

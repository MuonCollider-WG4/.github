# Muon Collider WG4

Organisation to handle version controlled lattice description files and other data for the Muon Collider Front End

[The Muon Collider web page](https://muoncollider.web.cern.ch/).

[A comprehensive description of the proposed facility](https://arxiv.org/abs/2504.21417).

<div align="center">
  <img src="https://muoncollider.web.cern.ch/sites/default/files/inline-images/IMCC-Logo-final-L_3_1.png" alt="muon collider logo" width="200">
</div>

## Version Control

Version control should be handled using Branches. A new version should be deployed for every significant report, paper, etc. Versions come in two flavours:
* __prerelease__: this is a snapshot intended to aid sharing lattices. Not everything is necessarily cleaned, but it provides a way of clearly tagging a particular blob
* __release__: this is a new version of the lattice intended to represent a fully updated lattice. All files should be updated as needed.

Versions should be stored in branches like

> [date]-prerelease

> [date]-release

I expect that there will not be more than one (pre)release per day. 

To make a new Branch, go to your repo in github.com. Near the top of the page, under the repo heading, there will be a piece of text saying _3 branches_. This is a link - click on it to get into the branch view. There will be a big green button at the top right that says _New Branch_. Click this and enter the name of your new branch.

Here is an example of the demonstrator github area to see how it might look:

![github screenshot](https://github.com/MuonCollider-WG4/.github/blob/main/images/Branches_MuonCollider-WG4_cooling_demonstrator.png)

## Git does the version control

Let git do the version control:- when you upload new lattice files to git, the old version is stored. You can list all the old versions by doing

> git log
```
commit 16ca897e9d873ddd1b3db4066c4dd5f70270dabc (HEAD -> master, origin/master, origin/HEAD)
Author: Chris Rogers <chris.rogers@stfc.ac.uk>
Date:   Thu Mar 26 14:32:48 2026 +0000

    Update to allow gap cells

commit 8c674067b97fe18f56fdd1913d37543cf778ce48
Author: Chris Rogers <chris.rogers@stfc.ac.uk>
Date:   Wed Feb 18 14:40:16 2026 +0000

    Update to documentation

commit 46ef04906ab153e845d0f5691581cc726c11f637
Merge: 4c51ec8 80b4d95
Author: Chris Rogers <chris.rogers@stfc.ac.uk>
Date:   Wed Feb 18 14:35:32 2026 +0000

    Merge branch 'master' of github.com:MuonCollider-WG4/cooling_demonstrator

commit 4c51ec808f53088e03791c69e58fdf93908a2aaf
Author: Chris Rogers <chris.rogers@stfc.ac.uk>
Date:   Wed Feb 18 14:35:07 2026 +0000

    Add link to 1M particle sample and log file
```

To get back to a particular commit, do:

> git checkout 4c51ec808f53088e03791c69e58fdf93908a2aaf

You will see a message about DETACHED_HEAD state to let you know that you are now pointing to a particular commit, and not the latest version. To go back to the latest version, do either

> git checkout master

in older repos (you will see `origin/master` near the top of the log output) or

> git checkout main

in newer repos (you will see `origin/main` near the top of the log output)

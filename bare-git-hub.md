---
description: >-
  A bare repository is a Git repository that contains only the contents of the
  .git/ directory. It is the purest form of the Git database, holding all commit
  history, branches, tags, and configurations,
---

# Bare git hub

So bare repo is nothing but it is like remote github so  buy setting up this in our local it contains all git meta data like commit history, branches, tags, and configurations so this can be setupped in that&#x20;

**Key Distinction:**

* **Non-Bare (Working Copy):** This is what you use on your local machine to edit code. It has a `.git/` folder _and_ your source files.
* **Bare (Central Hub):** This is located on a server (or a shared network drive) and acts as the synchronization point. It only contains the repository metadata.

2\. Why Use a Bare Repository?The primary purpose of a bare repository is to act as a **central remote** for team collaboration, similar to how GitHub or GitLab works.

* **Prevents Conflicts:** Pushing changes into a non-bare repository can cause conflicts with the active, checked-out files on that machine. A bare repo is designed _only_ to receive pushes safely.
* **Decentralized Access:** It allows team members to push and pull changes without needing an internet connection (if hosted on a local network) or relying on a third-party service.
* **Standard Practice:** It is the industry standard for hosting source control.

3\. Workflow & Branch ManagementAll development activities—creating branches, committing code, merging, and switching branches—happen in your local, non-bare working copy. The bare repo merely stores the completed history.3.1 Local Workflow CommandsFrom your local working directory:

| Command                         | Action                                              |
| ------------------------------- | --------------------------------------------------- |
| `git checkout -b <branch-name>` | Create and switch to a new local branch.            |
| `git commit -m "..."`           | Save changes locally on your branch.                |
| `git push origin <branch-name>` | Share your local branch with the central bare repo. |
| `git pull origin <branch-name>` | Get updates from the central bare repo.             |

4\. Setup Guide: Creating a Local Bare RepoFollow these steps to set up a bare repository on a shared machine or network drive:Step 1: Create the Bare RepositoryNavigate to the shared location (e.g., a shared folder `S:/Projects/` on a network drive) and initialize the bare repository:bash

```
cd /path/to/shared/location/
mkdir website-project.git
cd website-project.git
git init --bare
```

Use code with caution._Note the `.git` suffix naming convention._&#x53;tep 2: Developers Clone the RepoEach team member navigates to their local machine/desktop and clones the shared bare repository:bash

```
cd ~/Desktop
git clone /path/to/shared/location/website-project.git
# This creates a non-bare working directory named 'website-project'
```

Use code with caution.Step 3: Pushing Branches for CollaborationA developer works in their local copy (`~/Desktop/website-project`), creates a new feature branch, and pushes it to the shared bare repo (`origin`):bash

```
# Developer A's Machine
cd ~/Desktop/website-project
git checkout -b feature/user-profile
# ... develop code and commit ...

git push origin feature/user-profile
```

Use code with caution.Step 4: Teammate Accesses the New BranchDeveloper B can now fetch that new branch from the central bare repo:bash

```
# Developer B's Machine
cd ~/Desktop/website-project
git fetch origin
git checkout feature/user-profile
```

<br>

# 🚀 Mastering Version Control: A Deep Dive into SVN & Mercurial

**💻 Name:** Raghav

---

## 📌 Introduction to Version Control Systems

Version Control Systems (VCS) are essential for managing software changes, enabling collaboration, and maintaining project history.

---

## 📂 Types of Version Control Systems

1. **🔗 Centralized (CVCS):** Single central server stores all versions (e.g., **Subversion (SVN)**).
2. **🌍 Distributed (DVCS):** Every user has a full repository copy (e.g., **Mercurial (Hg)**).

---

## ❓ Why Use Version Control?

👉 Tracks all changes and keeps a history
👉 Supports collaboration among developers
👉 Enables rollback to previous versions
👉 Facilitates branching/merging for testing

---

## 🏰 Subversion (SVN)

_A Centralized Version Control System_

### 🌟 Key Features

-   📌 Centralized repository
-   🔄 Revision-based tracking (r1, r2, ...)
-   ⚡ Atomic commits
-   🌲 Directory-based branching

---

### ⚙️ SVN Command Workflow

#### 🛠 Step 1: Verify Installation

```bash
svn --version
```

![SVN Installation](https://raw.githubusercontent.com/git-raghav/SVN-Hg-Demo/main/images/image1.png)

#### 📝 Step 2: Create Repository & Standard Structure

```bash
svnadmin create C:\Users\ajayr\Raghav-SVN-Repo
cd C:\Users\ajayr
mkdir Raghav-SVN-Temp
cd Raghav-SVN-Temp
mkdir trunk branches tags
svn import . file:///C:/Users/ajayr/Raghav-SVN-Repo -m "Raghav: Initial structure"
```

![SVN Directory Creation](https://raw.githubusercontent.com/git-raghav/SVN-Hg-Demo/main/images/image2.png)
![SVN Directory Creation](https://raw.githubusercontent.com/git-raghav/SVN-Hg-Demo/main/images/image3.png)

#### ✍️ Step 3: Checkout Trunk & Add File

```bash
svn checkout file:///C:/Users/ajayr/Raghav-SVN-Repo/trunk Raghav-SVN-Trunk
cd Raghav-SVN-Trunk
echo "Hello from Raghav's SVN trunk!" > trunk-file.txt
svn add trunk-file.txt
svn commit -m "Raghav: First trunk commit"
```

![SVN Commit](https://raw.githubusercontent.com/git-raghav/SVN-Hg-Demo/main/images/image4.png)
![SVN Commit](https://raw.githubusercontent.com/git-raghav/SVN-Hg-Demo/main/images/image5.png)

#### 🔀 Step 4: Branching & Merging

```bash
# Create branch
svn copy file:///C:/Users/ajayr/Raghav-SVN-Repo/trunk file:///C:/Users/ajayr/Raghav-SVN-Repo/branches/raghav-feature -m "Raghav: Feature branch"

# Switch to branch
svn switch file:///C:/Users/ajayr/Raghav-SVN-Repo/branches/raghav-feature

# Edit in branch
echo "Branch work by Raghav" >> branch-file.txt
svn add branch-file.txt
svn commit -m "Raghav: Branch commit"

# Merge to trunk
svn switch file:///C:/Users/ajayr/Raghav-SVN-Repo/trunk
svn merge file:///C:/Users/ajayr/Raghav-SVN-Repo/branches/raghav-feature
svn commit -m "Raghav: Merged branch"
```

![SVN Branching & Merging](https://raw.githubusercontent.com/git-raghav/SVN-Hg-Demo/main/images/image6.png)
![SVN Branching & Merging](https://raw.githubusercontent.com/git-raghav/SVN-Hg-Demo/main/images/image7.png)
![SVN Branching & Merging](https://raw.githubusercontent.com/git-raghav/SVN-Hg-Demo/main/images/image8.png)
![SVN Branching & Merging](https://raw.githubusercontent.com/git-raghav/SVN-Hg-Demo/main/images/image9.png)

### ⚙️ Essential SVN Commands

| 🏷 Command                      | 📚 Description          |
| ------------------------------ | ----------------------- |
| `svn checkout <repo-url>`      | 🔄 Get a working copy   |
| `svn commit -m "Message"`      | 💾 Save changes to repo |
| `svn merge <branch-url>`       | 🔀 Merge branches       |
| `svn resolve --accept working` | ✅ Resolve conflicts    |

---

## 🔄 Mercurial (Hg)

_A Distributed Version Control System_

### 🌟 Key Features

-   🌍 Distributed repositories
-   ⚡ Atomic commits
-   🔀 Simple branching/merging

---

### ⚙️ Mercurial Command Workflow

#### 🛠 Step 1: Verify Installation

```bash
hg --version
```

![Mercurial Installation](https://raw.githubusercontent.com/git-raghav/SVN-Hg-Demo/main/images/image10.png)

#### 📂 Step 2: Initialize Repository & Commit

```bash
cd C:\Users\ajayr
mkdir Raghav-Hg-Repo
cd Raghav-Hg-Repo
hg init
echo "Mercurial demo by Raghav" > hg-file.txt
hg add hg-file.txt
hg commit -m "Raghav: First commit"
```

![Mercurial Commit](https://raw.githubusercontent.com/git-raghav/SVN-Hg-Demo/main/images/image11.png)
![Mercurial Commit](https://raw.githubusercontent.com/git-raghav/SVN-Hg-Demo/main/images/image12.png)

#### 🔀 Step 3: Branching & Merging

```bash
# Create branch
hg branch raghav-feature

# Edit in branch
echo "Branch changes by Raghav" >> hg-file.txt
hg commit -m "Raghav: Branch commit"

# Merge to default
hg update default
hg merge raghav-feature
hg commit -m "Raghav: Merged branch"
```

![Mercurial Branching & Merging](https://raw.githubusercontent.com/git-raghav/SVN-Hg-Demo/main/images/image13.png)
![Mercurial Branching & Merging](https://raw.githubusercontent.com/git-raghav/SVN-Hg-Demo/main/images/image14.png)
![Mercurial Branching & Merging](https://raw.githubusercontent.com/git-raghav/SVN-Hg-Demo/main/images/image15.png)

### ⚙️ Essential Mercurial Commands

| 🏷 Command                | 📚 Description             |
| ------------------------ | -------------------------- |
| `hg init`                | 🚀 Initialize a repository |
| `hg commit -m "Message"` | 💾 Save changes locally    |
| `hg merge <branch>`      | 🔀 Merge branches          |
| `hg resolve --mark`      | ✅ Mark conflicts resolved |

---

## ⚖️ SVN vs. Mercurial: Quick Comparison

| Feature      | 🏰 SVN                  | 🔄 Mercurial    |
| ------------ | ----------------------- | --------------- |
| Type         | 🔗 Centralized          | 🌍 Distributed  |
| Offline Work | ❌ Limited              | ✅ Full support |
| Branching    | 📂 Directory-based      | ⚡ Lightweight  |
| Performance  | 🐢 Slower for big repos | 🚀 Faster       |

---

## 🏆 Best Practices

👍 Use **SVN** for centralized team workflows.
👍 Use **Mercurial** for distributed/offline work.
👍 Write clear commit messages (e.g., `"Raghav: Fixed login bug"`).

---

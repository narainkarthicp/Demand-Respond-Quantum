# Git + GitHub SSH Setup and Workflow

## 1. Generate SSH Key (Per System)

Run:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Press `Enter` for default location.

---

## 2. Start SSH Agent

```bash
eval "$(ssh-agent -s)"
```

---

## 3. Add SSH Key

```bash
ssh-add ~/.ssh/id_ed25519
```

---

## 4. Copy Public Key

```bash
cat ~/.ssh/id_ed25519.pub
```

Copy the full output.

---

## 5. Add Key to GitHub

Open:

https://github.com/settings/keys

- Click `New SSH key`
- Title:
  - `office-laptop`
  - `desktop`
  - `ubuntu-server`
- Paste the public key
- Click `Add SSH key`

---

## 6. Test SSH Connection

```bash
ssh -T git@github.com
```

Expected:

```text
Hi username! You've successfully authenticated...
```

---

# Clone Repository on New System

```bash
git clone git@github.com:username/repository.git
```

---

# Essential Git Workflow

## Daily Safe Workflow

### 1. Check Status

```bash
git status
```

---

### 2. Pull Latest Changes Before Working

```bash
git pull origin main
```

---

### 3. Add Changes

Add all files:

```bash
git add .
```

Or specific file:

```bash
git add filename
```

---

### 4. Commit Changes

```bash
git commit -m "meaningful commit message"
```

Examples:

```bash
git commit -m "Added ROS2 demand response notes"
git commit -m "Fixed launch file issue"
git commit -m "Updated documentation"
```

---

### 5. Push Changes

```bash
git push origin main
```

---

# Recommended Workflow Before Every Push

```bash
git status
git pull origin main
git add .
git commit -m "your message"
git push origin main
```

---

# Useful Commands

## See Commit History

```bash
git log --oneline
```

---

## Check Remote URL

```bash
git remote -v
```

---

## See Current Branch

```bash
git branch
```

---

## Create New Branch

```bash
git checkout -b feature-name
```

---

## Switch Branch

```bash
git checkout main
```

---

# Good Practices

## DO

- Pull before pushing
- Use meaningful commit messages
- Commit small logical changes
- Keep `main` stable
- Use branches for experiments/features
- Push regularly

---

## DON'T

- Force push unnecessarily
- Commit large unrelated changes together
- Commit passwords/API keys
- Edit directly on GitHub and locally at same time without pulling

---

# Multi-System Usage

Each system should:

- Generate its own SSH key
- Add its public key to GitHub
- Clone repository separately

Do NOT share:

```text
~/.ssh/id_ed25519
```

Only public key should be shared:

```text
~/.ssh/id_ed25519.pub
```

---

# Typical Example Workflow

```bash
git pull origin main
# do your work

git status
git add .
git commit -m "Updated ROS2 notes"
git push origin main
```

# Git Setup Guide

## Step 1: Configure Git
To properly use Git, configure your user information:
```sh
git config --global user.name "Your Name"
git config --global user.email "yourname@example.com"
```
Verify your configuration:
```sh
git config --get user.name
git config --get user.email
```

Set the default branch to `main`:
```sh
git config --global init.defaultBranch main
```

Set default branch reconciliation behavior:
```sh
git config --global pull.rebase false
```

---

## Step 2: Create an SSH Key
Check if you already have an SSH key:
```sh
ls ~/.ssh/id_ed25519.pub
```
If you see `No such file or directory`, generate a new SSH key:
```sh
ssh-keygen -t ed25519
```
When prompted for a location, press `Enter`. You may enter a passphrase or leave it empty.

---

## Step 3: Add SSH Key to GitHub
1. Log into [GitHub](https://github.com/).
2. Click on your profile picture → **Settings**.
3. On the left, click **SSH and GPG keys**.
4. Click **New SSH Key**.
5. Name your key (e.g., `linux-ubuntu`).
6. Copy your SSH key:
   ```sh
   cat ~/.ssh/id_ed25519.pub
   ```
7. Paste the key into GitHub and click **Add SSH Key**.

---

## Step 4: Test the SSH Connection
Run:
```sh
ssh -T git@github.com
```
If you see a fingerprint warning, verify it matches one of GitHub's official fingerprints. If it does, then type `yes` :
```
SHA256:uNiVztksCsDhcc0u9e8BujQXVUpKZIDTMczCvj3tD2s (RSA)
SHA256:br9IjFspm1vxR3iA35FWE+4VTyz1hYVLIE2t1/CeyWQ (DSA - closing down)
SHA256:p2QAMXNIC1TJYWeIOttrVc98/R1BUFWu3/LiyKgUfQM (ECDSA)
SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU (Ed25519)
```
Expected output:
```
Hi USERNAME! You've successfully authenticated, but GitHub does not provide shell access.
```

You are now ready to use Git with SSH authentication! 🎉

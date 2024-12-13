. Set Up SSH Authentication (Recommended)
a. Check for Existing SSH Keys

Run this command to see if you already have an SSH key:

ls -al ~/.ssh
Look for files named id_rsa and id_rsa.pub. If they exist, you already have an SSH key pair. If not, proceed to the next step.

b. Generate a New SSH Key

Generate an SSH key pair:

ssh-keygen -t ed25519 -C "your_email@example.com"
Replace your_email@example.com with your GitHub email address.
Press Enter to accept the default file location.
Set a passphrase or leave it empty.
c. Add the SSH Key to the SSH Agent

Start the SSH agent:

eval "$(ssh-agent -s)"
Add your SSH key:

ssh-add ~/.ssh/id_ed25519
d. Add the SSH Key to GitHub

Copy the SSH public key:
cat ~/.ssh/id_ed25519.pub
Go to your GitHub account settings:
Navigate to Settings > SSH and GPG keys > New SSH key.
Paste the public key and save.
e. Test the SSH Connection

Test the connection to GitHub:

ssh -T git@github.com
If successful, you'll see a message like:

Hi <username>! You've successfully authenticated.# Configuration

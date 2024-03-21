# Gitcommands
1.  Open a terminal on your Ubuntu system and run the following command to generate an SSH key pair:

    ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

    Replace your_email@example.com with the email address associated with your GitHub account. Press Enter to accept the default file location (~/.ssh/id_rsa) 
    and to leave the passphrase empty for simplicity or set a passphrase as per your preference.

2.  Add SSH Key to SSH Agent:
    Start the SSH agent by running the following command:

    eval "$(ssh-agent -s)"

    Then add your SSH private key to the SSH agent by running:
    
    ssh-add ~/.ssh/id_rsa
    
3  Copy SSH Public Key to GitHub:
    Use the following command to display your SSH public key:

    cat ~/.ssh/id_rsa.pub
    
    Copy the entire output.

4.  Add SSH Public Key to GitHub:
    Log in to your GitHub account and go to Settings > SSH and GPG keys > New SSH key.
    Paste your SSH public key into the "Key" field and give it a meaningful title.
    Click "Add SSH key" to add the key to your GitHub account.

5.  Test SSH Connection:
    To test if your SSH key is set up correctly, run the following command:

    ssh -T git@github.com
    
    You may see a warning about authenticity of the host, type yes to continue.
    If everything is set up correctly, you should see a message confirming that you've successfully authenticated.

6.  Update Git Remote URL:
    Finally, update the remote URL of your Git repository to use the SSH URL instead of HTTPS. Navigate to your repository directory and run:

    git remote set-url origin git@github.com:username/repository.git
    
    Replace username/repository with your GitHub username and repository name.

    After completing these steps, you should be able to interact with your GitHub repositories using SSH authentication without encountering the authentication error.




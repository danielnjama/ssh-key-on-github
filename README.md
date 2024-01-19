# ssh-key-on-github

A Step-by-Step Guide on Generating and Uploading SSH Keys to GitHub
introduction

Secure Shell (SSH) keys are a powerful and secure way to authenticate yourself with remote servers and services. GitHub, a widely-used platform for version control and collaborative development, allows users to upload SSH keys for secure and seamless access to repositories. In this guide, we will walk you through the process of generating SSH keys and uploading them to your GitHub account.

Prerequisites

Before we begin, ensure that you have the following:

A GitHub account: If you don't have one, you can create it here.

Git installed on your machine: You can download it here.

Step 1: Generating SSH Keys

Open a terminal on your local machine, and follow these steps to generate your SSH keys:

# Generate SSH key pair 
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

Replace "your_email@example.com" with the email associated with your GitHub account. Press Enter to accept the default file location, and optionally, set a passphrase for an added layer of security.

Step 2: Adding SSH Key to SSH Agent (Optional)

If you want to use an SSH agent to manage your keys, run the following commands:

eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa

Step 3: Copying the Public Key

To upload your public key to GitHub, you need to copy its contents. Run the following command:

# Copy public key to clipboard 
pbcopy < ~/.ssh/id_rsa.pub

If the pbcopy command is not available on your system, open the public key file (~/.ssh/id_rsa.pub) in a text editor and copy its contents.

Step 4: Adding SSH Key to GitHub

Log in to your GitHub account.

Navigate to "Settings" > "SSH and GPG keys."

Click on "New SSH key" or "Add SSH key."

Provide a title for the new key and paste your public key into the "Key" field.

Click "Add SSH key."

Step 5: Testing the Connection

To ensure everything is set up correctly, test the connection to GitHub:

ssh -T git@github.com

If successful, you should see a message indicating a successful authentication.

Conclusion

Congratulations! You have successfully generated and uploaded your SSH key to GitHub. You can now use this key for secure interactions with your repositories, making your development workflow smoother and more secure.

# Step-by-Step Guide on Setting Up Git and GitHub on a New Machine

Setting up Git and GitHub on a new machine is an important task for developers, as it allows you to manage your code, collaborate with others, and keep your projects organized. This guide will walk you through the process step-by-step.

## Step 1: Install Git

Git is a distributed version control system that you need to install on your machine to manage your repositories.

1. **Download Git:**
   - **Windows:** Visit [Git for Windows](https://gitforwindows.org/) and download the installer.
   - **macOS:** Use Homebrew. If you don't have Homebrew, install it first by running:
     ```bash
     /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
     ```
     Then install Git by running:
     ```bash
     brew install git
     ```
   - **Linux:** Use your package manager. For example, on Ubuntu:
     ```bash
     sudo apt update
     sudo apt install git
     ```

2. **Install Git:**
   - **Windows:** Run the downloaded installer and follow the installation wizard. Use the default settings unless you have specific requirements.
   - **macOS and Linux:** The installation commands above will automatically install Git.

3. **Verify Installation:**
   Open a terminal or command prompt and run:
   ```bash
   git --version
   ```
   You should see the installed Git version, confirming that Git is successfully installed.

## Step 2: Configure Git

After installing Git, you need to configure it with your user information.

1. **Set Your Username:**
   ```bash
   git config --global user.name "Your Name"
   ```

2. **Set Your Email:**
   ```bash
   git config --global user.email "your.email@example.com"
   ```

3. **Verify Configuration:**
   ```bash
   git config --list
   ```
   This command will display your Git configuration settings.

## Step 3: Create a GitHub Account

If you don't already have a GitHub account, you need to create one.

1. **Sign Up:**
   - Go to [GitHub](https://github.com/).
   - Click on "Sign up" and follow the instructions to create your account.

2. **Verify Email:**
   GitHub will send you a verification email. Follow the link in the email to verify your account.

## Step 4: Generate SSH Key

To securely connect your local machine to GitHub, you need to generate an SSH key.

1. **Generate the Key:**
   Open a terminal or command prompt and run:
   ```bash
   ssh-keygen -t ed25519 -C "your.email@example.com"
   ```
   Press Enter to accept the default file location and name. Next, you'll be prompted to enter a passphrase. You can choose to enter a passphrase or leave it empty.

2. **Add SSH Key to the SSH Agent:**
   ```bash
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_ed25519
   ```

3. **Copy SSH Key to Clipboard:**
   - **Windows:** Use `clip` to copy the key:
     ```bash
     clip < ~/.ssh/id_ed25519.pub
     ```
   - **macOS:** Use `pbcopy`:
     ```bash
     pbcopy < ~/.ssh/id_ed25519.pub
     ```
   - **Linux:** Use `xclip`:
     ```bash
     xclip -selection clipboard < ~/.ssh/id_ed25519.pub
     ```

## Step 5: Add SSH Key to GitHub

1. **Go to GitHub Settings:**
   - Click on your profile picture in the top-right corner and select "Settings."

2. **SSH and GPG Keys:**
   - In the left sidebar, click on "SSH and GPG keys."

3. **Add New SSH Key:**
   - Click on "New SSH key."
   - Paste your copied SSH key into the "Key" field.
   - Give it a descriptive title, e.g., "My Laptop."
   - Click "Add SSH key."

## Step 6: Clone a Repository

Now that everything is set up, you can clone a repository to your local machine.

1. **Go to a Repository:**
   - Navigate to the repository you want to clone on GitHub.

2. **Clone the Repository:**
   - Click on the "Code" button and copy the SSH URL.
   - In your terminal or command prompt, navigate to the directory where you want to clone the repository and run:
     ```bash
     git clone git@github.com:username/repository.git
     ```

## Step 7: Start Using Git and GitHub

With everything configured, you are now ready to start using Git and GitHub.

1. **Create a New Repository:**
   - On GitHub, click on the "+" icon in the top-right corner and select "New repository."

2. **Initialize the Repository:**
   - Follow the instructions to create a new repository.

3. **Connect Local Repository to GitHub:**
   - In your terminal, navigate to your project directory and initialize Git:
     ```bash
     git init
     ```
   - Add the remote repository:
     ```bash
     git remote add origin git@github.com:username/repository.git
     ```

4. **Add, Commit, and Push Changes:**
   - Add files to staging:
     ```bash
     git add .
     ```
   - Commit changes:
     ```bash
     git commit -m "Initial commit"
     ```
   - Push to GitHub:
     ```bash
     git push -u origin master
     ```

Congratulations! You have successfully set up Git and GitHub on your new machine. You can now manage your code, collaborate with others, and contribute to projects.

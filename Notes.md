# Automaticaly make a list of your gists.

Use the workflow file, make your own personal access token with org, gists, and repo.
- repo - to update your repository storing this project and commit the output results (the Index / README.md)
- admin:org read - classic token gave error in workflow for me without this permission
- gists

by default, this runs weekly and if no changes, it won't perform an update/commit of the REAME.md in the repository.

## License

1) You are encourged to use the code.
2) Give credit. Thank you.

## Notes about the code

I used sed mostly, awk had trouble when the descriptions had multiple words (spaces). JSON is likely a good choice as an alternative.<br>
The **gh cli** output varies some by OS. For example, in GitHub workflows (ubuntu) the modification is a zulu date-time format but in Windows it says 'a few months ago'.

There is one character escape, the pipe | because I formated with markdown tales and that seemed to throw off my parsing early on. Beware of other possible characters that will give odd markdown results.

To use this for your Private gists, some instances of 'Public' are changed to 'Secret' and other context use 'Private'

-----

### Step 1: Generate a Personal Access Token (PAT)

1. **Go to GitHub Settings**:

    - Log in to your GitHub account.
    - Navigate to the **Settings** page by clicking on your profile picture in the top-right corner and selecting **Settings**.
2. **Access Developer Settings**:

    - Scroll down to the bottom in the left-hand menu and click on **Developer settings**.
3. **Go to Personal Access Tokens**:

    - Under **Developer settings**, click on **Personal access tokens** &gt; **Tokens (classic)**.
4. **Generate New Token**:

    - Click on the **Generate new token** button.
    - Choose **"Fine-grained token"** if available, otherwise proceed with the classic token.
5. **Set Token Name and Expiration**:

    - Enter a descriptive name, e.g., **Index Public Gists Project**.
    - Set an expiration date. A shorter expiration (e.g., 30 days) is recommended for security, but you can adjust this based on your project needs.
6. **Select Scopes**:

    - For the **index-public-gists**project, you need the following scopes:
        - `gist`: Allows access to manage gists, including listing public gists.
    - If using repositories or other features later, you can add more scopes as needed.
7. **Generate Token**:

    - Click **Generate token**.
    - Copy the token immediately and save it securely. **You won’t be able to see it again!**

* * *

### Step 2: Add the PAT to GitHub Repository Secrets

1. **Open Your Repository**:

    - Go to your GitHub repository for the **index-public-gists** project.
2. **Navigate to Settings**:

    - Click on the **Settings** tab in the repository.
3. **Go to Secrets and Variables**:

    - In the left-hand menu, select **Secrets and variables** &gt; **Actions**.
4. **Add a New Secret**:

    - Click **New repository secret**.
    - For the **Name**, enter a descriptive name, e.g., `PAT`.
    - For the **Value**, paste the Personal Access Token you generated.
    - Click **Add secret**.

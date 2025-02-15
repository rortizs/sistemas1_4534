# Task 1

## Title Project = Landing Page

Below is a step-by-step tutorial on how to manage version control for a landing page (HTML5, Bootstrap5, MVC architecture) with a team of 3 using Git and GitHub. It details the creation of the repository, cloning, creating branches for specific tasks, and merging changes into the main branch

## Scenario and Roles

• Project: Landing page with HTML5, Bootstrap5, following an MVC structure (Model, View, Controller).
promotions 5 points final (\*)
• Members: 1. Leader (Member 3): Creates the main repository and is in charge of merging the changes. Task: create the Bootstrap5 base CSS and prototype/wireframe 2. Member 1: Develop the header (including logo) and the navigation bar (navbar) 3. Member 2: Develop the main and the footer

    Landing Page mvc structure, this columns =
      - Header --> Logo, Menu
      - Navbar  --> Vertical Menu
      - Content Main --> Content
      - Footer  --> information, social networks, address, phones, contactme

### Member Leader

1. Creating the Main Repository (Leader)
   1.1. Log in to the leader's GitHub account.
   1.2. Click on New repository and name it, for example: `landing-page-mvc`
   1.3. Add a brief description and choose visibility (public or private).
   1.4. (Optional but recommended) Check the box for Initialize this repository with a README.
   1.5. Click Create repository.

## Clone git repository

2.1. Clone the Repository (Leader) On your local machine, open the terminal and run:
`bash git clone https://github.com/NombreUsuario/landing-page-mvc.git
   cd landing-page-mvc`
3.2. Creating the Initial Structure

Suppose you want to follow an MVC structure. The leader can create a directory tree as a reference:
`bash mkdir -p app/{models,views,controllers}
mkdir -p public/{css,js,images}
touch index.html`

app will contain the MVC logic (model, views, controllers). public contains the static resources (css, js, images), and index.html will serve as the entry point.

1.3. Commit and Initial Push (Leader)

Adds and commits initial changes:
`bash git add .
git commit -m "create: Create MVC base structure for the landing page"
git push origin main`

The repository on GitHub now has the base structure.

## Cloning the Repository by Other Members

Both Member 1 and Member 2 must clone the repository that the leader created:
`bash git clone https://github.com/NombreUsuario/landing-page-mvc.git
cd landing-page-mvc`

Replace Username with the leader's actual GitHub username from member ship example member 1 or memeber 2.

### Creating Branches for Specific Tasks

3.1. Member 1 (Header, Logo, Navbar)
3.1.1. First make sure you are on the main branch:
`bash git checkout main
     git pull origin main`
3.2. Create and switch to the new branch for the task:
`bash git checkout -b feature/header_navbar`

3.3 Start working on the relevant files. For example, modify index.html, add the logo to public/images, etc.

4.1 Integrator 2 (Main, Footer)
4.1.1. Make sure you are on the main branch:
`bash git checkout main
     git pull origin main`
4.2 Create and switch to the new branch:
`bash git checkout -b feature/main_footer`
4.3 Implement the main content and footer in the corresponding files (index.html, app/views/, etc.).

5.1. Lead (Member 3) (Bootstrap5, Wireframe/Prototype)
Although the lead already has the cloned repository, he follows the same process for his own task:
5.2. Make sure he is in main:
`bash git checkout main
    git pull origin main`
5.2 Create and switch to the new branch:
`bash git checkout -b feature/bootstrap_wireframe`

Add the Bootstrap5 CDN to index.html or include the Bootstrap5 files in the public/css folder. Create a wireframe in the HTML for others to use.

## Individual Work on Branches and Commits

Each member works on his or her branch. After making changes, atomic commits are made with clear messages. For example, Member 1 implements the header, then makes a commit:
`bash git add .
git commit -m "feat: Agregar header con logo y navbar principal"`

It is recommended to make commits every time a functional part is completed.

## Uploading Branches to the Remote Repository

Once each member (1 and 2) and the leader (3) finish their task, they upload their branch to the remote repository:
`bash git push origin feature/header_navbar # Member 1
 git push origin feature/main_footer # Member 2
 git push origin feature/bootstrap_wireframe #Leader`

## Creating Pull Requests on GitHub

### Commands to Create Pull Request and Merge from Terminal

1.1. Install GitHub CLI (if you don't have it already)
• Windows: Download from GitHub CLI Releases. `https://github.com/cli/cli/releases`
• macOS / Linux: Use Homebrew or apt, as appropriate, for example:
`bash brew install gh` or linux `bash sudo apt-get install gh`.

### Authenticate in GitHub CLI

Open the terminal and run:
`bash gh auth login`

Follow the instructions to authenticate with your GitHub account.

Creating a Pull Request from the Terminal

Suppose the leader checks out member 1's branch (for example, feature/header_navbar). To create the Pull Request pointing to main, do the following:
`bash

### Move to the feature/header_navbar branch (if you're not already there)

git checkout feature/header_navbar

### Update your local branch if necessary

git pull origin feature/header_navbar

### Create the Pull Request (PR)

gh pr create \
--title "Header & Navbar Implementation" \
--body "Adding header with logo and navbar for landing page." \
--base main \
--head feature/header_navbar`

This command generates the PR on GitHub with the specified title and description.

### Merge the Pull Request from the Terminal

After creating the PR, you can review it. Once you confirm that everything is in order, you can merge the Pull Request:

1. Check the Pull Request number (for example, #5) in the Terminal or on GitHub.
2. Run the following command:
   `bash
gh pr merge <numero_de_pr> --merge
`
   example:
   `bash
gh pr merge 5 --merge
`
   This will merge the main branch with a merge commit. If you want to squash or rebase instead of merging, use the --squash or --rebase flags.

## commit example

Commit -m "Create: "
commit -m "update:"
commit -m "delete: "
commit -m "fix: "

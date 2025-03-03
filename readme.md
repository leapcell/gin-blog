# Gin Example Project Deployment Guide on Leapcell

## Introduction

This is an example project built with the Gin web framework. The main objective of this project is to teach users how to deploy a Gin application on the Leapcell platform. Whenever you make changes to the Markdown files in the `content` directory and perform a `git merge` into the `main` branch, an automatic deployment will be triggered on Leapcell.

## Project Structure

```
.
├── LICENSE                 # License file for the project
├── content                 # Directory containing Markdown files for blog posts
│   ├── first-review.md     # First sample blog post in Markdown
│   └── second.md           # Second sample blog post in Markdown
├── go.mod                  # Go module file, specifying project dependencies
├── go.sum                  # Go sum file, recording the expected cryptographic checksums of dependencies
├── main.go                 # The main entry point of the Gin application
├── static                  # Directory for static files
│   └── images              # Sub - directory for image files
│       └── logo.png        # Example logo image
└── templates               # Directory for HTML templates
    ├── index.tmpl          # Template for the home page
    └── single.tmpl         # Template for a single blog post
```

## Prerequisites

- A GitHub (or other Git - based) repository for your project.
- A Leapcell account. You can sign up at [Leapcell's official website](https://leapcell.io).
- Basic knowledge of Git commands and Go programming.
- Go programming environment installed on your local machine.

## Local Setup

1. **Clone the Repository**
   ```bash
   git clone https://github.com/leapcell/gin-blog
   cd gin-blog
   ```
2. **Install Dependencies**
   ```bash
   go mod tidy
   ```
3. **Run the Application Locally**
   ```bash
   go run main.go
   ```
   Then, open your browser and visit `http://localhost:8080` to see the application running.

## Deployment on Leapcell

1. **Connect Your Repository to Leapcell**
   - Log in to your Leapcell account.
   - Navigate to the project creation page and select the option to connect your Git repository (e.g., GitHub).
   - Authorize Leapcell to access your repository and choose the `main` branch.
2. **Configure the Deployment**
   - **Build Command**: In Leapcell, set the build command to `go build -o main main.go`. This will compile your Go application.
   - **Start Command**: Set the start command to `./main`. This will start your compiled application.
3. **Initial Deployment**
   - After configuration, Leapcell will automatically start the first deployment. You can monitor the deployment progress on the Leapcell dashboard.

## Try Making Changes and Merging to the Main Branch

1. **Modify a Blog Post**
   - Open one of the Markdown files in the `content` directory, such as `first - review.md`.
   - Make some changes to the content, for example, add a new paragraph or correct a typo.
2. **Stage and Commit Your Changes**
   ```bash
   git add content/first - review.md
   git commit -m "Update the content of first - review.md"
   ```
3. **Create a New Branch (Optional but Recommended)**
   ```bash
   git checkout -b new - content - branch
   ```
4. **Merge Your Changes to the Main Branch**
   - First, switch back to the `main` branch:
     ```bash
     git checkout main
     ```
   - Then, pull the latest changes from the remote `main` branch:
     ```bash
     git pull origin main
     ```
   - Finally, merge your changes from the new branch (if you created one):
     ```bash
     git merge new - content - branch
     ```
   - Push the updated `main` branch to the remote repository:
     ```bash
     git push origin main
     ```
5. **Watch the Automatic Deployment**
   - Once you push the changes to the `main` branch, Leapcell will detect the changes and start an automatic deployment.
   - Check the Leapcell dashboard to see the deployment progress. After the deployment is successful, you can visit your application's URL on Leapcell to see the updated content.

## Troubleshooting

- If the deployment fails, check the deployment logs on Leapcell. They usually provide detailed error messages.
- Ensure that all the dependencies in the `go.mod` file are correctly specified and compatible with each other.

## Conclusion

By following this guide, you should be able to deploy your Gin application on Leapcell and experience the automatic deployment feature when you update your content. Try making more changes to your blog posts and enjoy the seamless deployment process!

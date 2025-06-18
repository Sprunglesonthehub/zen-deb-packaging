# File: README.md

# Zen Browser Debian Packaging

This repository automatically builds a `.deb` package for the [Zen Browser (Firefox fork)](https://github.com/zen-browser/desktop) for Debian-based Linux distributions like Ubuntu, Debian, and Mint.

## How It Works

This repository contains a GitHub Actions workflow that:
1.  Triggers either manually or on a push to the `main` branch.
2.  Determines which version of Zen Browser to package.
3.  Downloads the official `zen.linux-x86_64.tar.xz` release from the upstream repository.
4.  Extracts the application and arranges its files into a standard Debian package structure, installing the browser into `/opt`.
5.  Adds a `.desktop` file for application menus and a symbolic link for command-line use.
6.  Builds the final `.deb` package.
7.  Uploads the package as a workflow artifact for you to download.

## Usage

### 1. Automatic Builds (for Testing)

Every time you push a change to the `main` branch of this repository, the workflow will automatically run. It will find the **latest** official Zen Browser release and build a "dev" package from it.

You can find the resulting `.deb` file by going to the **Actions** tab, clicking on the completed workflow run, and looking for the **Artifacts** section on the summary page.

### 2. Manual Builds (for a Specific Version)

This is the primary way to create a package for a specific version.

1.  Go to the **Actions** tab in this repository.
2.  On the left, click on the **"Build Zen Browser .deb Package"** workflow.
3.  Click the **"Run workflow"** dropdown button on the right.
4.  In the **"Zen Browser version tag to build"** field, enter the official release tag you want to package (e.g., `v1.2.3`).
5.  Click the green **"Run workflow"** button.

The action will run and the final `.deb` package will be available as an artifact, just like with the automatic builds.

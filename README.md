# crepo - Create GitHub Repository Script

This Bash script automates the process of creating a new repository on GitHub, initializing a local repository, and pushing the initial commit. 

## Features

- Creates a new GitHub repository (public or private).
- Initializes a local Git repository.
- Adds a README file and pushes the initial commit to GitHub.

## Prerequisites

- [Git](https://git-scm.com/)
- [jq](https://stedolan.github.io/jq/)
- A GitHub account and a [personal access token](https://github.com/settings/tokens)

## Installation

### Install Git and jq

#### Debian-based Linux (e.g., Debian, Ubuntu)

```sh
sudo apt update
sudo apt install -y git jq
```

#### Arch Linux

```sh
sudo pacman -Syu
sudo pacman -S git jq
```

#### macOS with Homebrew

```sh
brew install git jq
```

### Clone the repository

```sh
git clone https://github.com/MarekCZFM/crepo.git
cd crepo
```

## Setup

### Adding to binaries directory or the PATH

#### Example of adding to binaries directory

```sh
sudo mv crepo /usr/local/bin/
sudo chmod +x /usr/local/bin/crepo
```

#### Adding to the PATH

***Replace /path/to/your/script with the path to your script***
```sh
export PATH=$PATH:/path/to/your/script
```

### Restart or reload your shell

#### Restart

```sh
exit
```

#### Reload on Bash
```sh
source ~/.bashrc
```

#### Reload on ZSH

```sh
source ~/.zshrc
```

## Usage

```sh
crepo "Repository name" [--public]
```

- Replace *Repository name* with the name of the new repository and add --public if you want the repository to be public
- The quotes are not required but if you add them you can type spaces which will be converted to dashes afterwards

### Examples

- Create a private repository:
```sh
crepo "My private repo"
```
*Resulting repository will be named: My-private-repo and will be private*

- Create a public repository:
```sh
crepo "My pubic repo" --public
```
*Resulting repository will be named: My-public-repo and will be public*


## Problems

### Entered the wrong credentials the first time starting my program / My credentials expired or changed

**Solution**: Delete the file *.github_credentials* in your home directory and restart the program:
```sh
rm ~/.github_credentials
crepo
```

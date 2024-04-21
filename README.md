# **Git & GitHub, Docker, VCS...**

This repository serves as a quick reference for essential Git and GitHub commands and Version Control System, organized for ease of use. 🚀

## Overview

Welcome to the Git and GitHub Commands repository — a comprehensive guide of ***Important Git and GitHub commands and concepts*** for developers at any stage of their development journey.
Here, you'll find a curated collection of commands carefully structured for ease of use, covering everything from fundamental Git basics to advanced GitHub collaboration strategies. This repository is your go-to resource.


## Pre-requisites and Installation

Before diving in, ensure you have the following pre-requisites:

1. **Git Bash:** Install Git Bash on your machine. You can download it from [git-scm.com](https://git-scm.com/downloads).
2. **GitHub Account:** Create an account on [GitHub](https://github.com) if you don't have one. This will enable you to explore and apply Git and GitHub commands in real-world scenarios.
3. **Command Line Interface (CLI):** Familiarize yourself with a command-line interface, such as the terminal on macOS/Linux or Command Prompt/PowerShell on Windows. Install one, if you don't have on your system.
4. **GitHub Authorization:** 
    1. **Using github-ssh:** Authorize GitHub with your terminal. Follow the instructions [here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh) to set up SSH keys for secure communication with GitHub.
    2. **Using github-CLI(Recommanded):** Authorize GitHub with GitHub Command Line itself. Open your terminal/powershell in system and type:

        For Linux

        ```
        > sudo apt-key adv-keyserver keyserver.ubuntu.com-recv-key C99B11DEB97541F0
        > sudo apt-add-repository -u https://cli.github.com/packages
        > sudo apt install gh
        ```

        For Windows

        ```
        > winget install gh
        ```

        Without personal access token, now just type:

        ```
        > gh auth login
        ```
        And follow the instructions and eventually it'll show a code(copy it), press enter, paste the code and complete the authorizations.
    3. **Using github-token:** Go to your GitHub account, Profile_image>Settings>Developer_Settings>Personal_access_tokens now click 'Generate token' button. 

        Enter your name, select permissions you need, and Generate token.

        Copy the generated token. **Note:** Token will only be shown once, show download it.

        Configure Git the token. Type the below command in terminal/perworshell to set token as credential helper for github:

        ```
        > git config --global credential.helper store
        ```
        
        Now you are ready to `clone` and `push` your local repository, just set the remote URL of the repository with your <username> and token:

        ```
        > git remote set-url origin https://<username>:<token>@github.com/<username>/<repository>.git
        ```

        Or

        ```
        > gh auth login --with-token <your_personal_access_token>
        ```

5. **Code Editor Integration:** If you haven't already, integrate your preferred code editor with GitHub. Most editors, such as Visual Studio Code, offer seamless GitHub integration.



## Learning Method: Learn and Practice

1. **Learn:** Explore the `docs/` directory for detailed documentation on different command categories.
2. **Practice:** Apply what you've learned by using Git and GitHub in real-world projects.
3. **Search:** If you don't understand something, just **Google it.**

## Contributing

Contributions are welcome! Open an issue or submit a pull request to add commands, suggest improvements, or report errors. Let's build a valuable resource for the developer community.

Let's learn, collaborate, and make the world of version control more accessible together! 🌐


## License

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This work is published under the [MIT](https://github.com/harsh-a-parihar/Git_and_Github_VCS/blob/main/LICENSE) License.
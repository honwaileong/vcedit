# Version Controlled Editor - A VIM plus Subversion Wrapper for System Configurations
## Introduction
The objective of this tool is to address challenges faced by system administrators in versioning and tracking changes made in system configuration scripts. 

In a conventional workflow of software development, a program source is cloned from a repository (like Github, Subversion) to a working directory, then it is edited, compiled and tested in an isolated environment (e.g. user own directory). The changes made in the working directory are committed back to the repository before it is deployed for production use. 

In the scenario of editing system configuration (usually files found under 'etc' directory of a system software), scripts are usually edited live and tested directly in a production environment (unless it is cost effective to have another testbed system with the exact configuration). This practice is fairly common. In situation where trials and errors type of editing are required to troubleshoot a system issue, it is not practical to follow the multi-steps software development workflow as mentioned above. 

In large system like HPC system, there are usually more than one system administrators logging into the system as root to edit the system files. It becomes untrackable what changes have been made by which system administrator. 

These two major issues can be addressed by using a text editor with version control capability. In this first prototype, a wrapper that combines VIM and Subversion are employed. 

## Installation and Setup

Clone "vcedit" tool from https://github.com/hwleong/vcedit

  $ git clone https://github.com/hwleong/vcedit
  $ export PATH=/path/to/vcedit


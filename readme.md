# Version Controlled Editor - A VIM plus Subversion Wrapper for System Administrators
## Introduction
The objective of this tool is to address challenges faced by system administrators in versioning and tracking changes made in system configuration scripts. 

In a conventional workflow of software development, a program source is cloned from a repository (like Github, Subversion) to a working directory, then it is edited, compiled and tested in an isolated environment (e.g. user own directory). The changes made in the working directory are committed back to the repository before it is deployed for production use. 

In the scenario of editing system configuration (usually found under 'etc' directory of a system software), scripts are usually edited live and tested directly in a production environment (unless it is cost effective to have another testbed system with the exact configuration). This practice is fairly common. 

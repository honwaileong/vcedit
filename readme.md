# Version Controlled Editor - A VIM plus Subversion Wrapper for System Configurations
## Introduction
The objective of this tool is to address challenges faced by system administrators in versioning and tracking changes made in system configuration scripts. 

In a conventional workflow of software development, a program source is cloned from a repository (like Github, Subversion) to a working directory, then it is edited, compiled and tested in an isolated environment (e.g. user own directory). The changes made in the working directory are committed back to the repository before it is deployed for production use. 

In the scenario of editing system configuration (usually files found under 'etc' directory of a system software), scripts are usually edited live and tested directly in a production environment (unless it is cost effective to have another testbed system with the exact configuration). This practice is fairly common. In situation where trials and errors type of editing are required to troubleshoot a system issue, it is not practical to follow the multi-steps software development workflow as mentioned above. 

In large system like HPC system, there are usually more than one system administrators logging into the system as root to edit the system files. It becomes untrackable what changes have been made by which system administrator. 

These two major issues can be addressed by using a text editor with version control capability. In this first prototype, a wrapper that combines VIM and Subversion are employed. 

## Installation and Configuration

Clone "vcedit" tool from https://github.com/hwleong/vcedit and set PATH environment variable. 

    $ git clone https://github.com/hwleong/vcedit
    $ export PATH=/path/to/vcedit

"vcedit" tool comes with a "vc.conf" configuration file. 

    $ cat vc.conf
    SSHOPTS="/usr/bin/ssh -q" 
    # User definable SSH options to be passed to Subversion when using svn+ssh repository. 
    # If undefined, the default is "/usr/bin/ssh -q". 
    SVNREPO=svn://repo.url.addr
    # Default SVN Repository URL to use when initializing version control in a new directory. 
    # If undefined, user will be prompted to key in a SVN Repository URL. 

By default, "vcedit" lookup for "vc.conf" file in the same directory where "vcedit" is installed, unless "-f" option is passed to "vcedit" command.

## Usage

    $ vcedit -h
    Usage: vcedit -d <repodir> -f <config_file> -r <svn_repo_url> -u <svn_user> <filename>
    Edit <filename>.
    
    Usage: vcedit -c <class>
    Switch to a different class. If <class> is not specified, list currently available class in remote repository.
    
    Usage: vcedit -i <filename>
    Show information of file. If <filename> is not specified, show information of current working directory.
    
    Usage: vcedit -l
    List files under the remote SVN repository.
    
    Usage: vcedit -v <filename>
    Show version changelog of file. If <filename> is not specified, show changelog of current working directory.
    
    Usage: vcedit -s <filename>
    Show status of file. If <filename> is not specified, show status of current working directory.

# TODO

**gitrepocheck** check for git repositories and report all changes. It is
intended to run automatically to check for exemple git repository in /etc where
files can be changed by automated process like OS upgrades.

# Usage

Without any parameters, gitrepocheck search for git repositories recursively
from the current working directory.

With pathnames separated by spaces, gitrepocheck check for git repositories
recusively from these pathnames.

gitrepocheck doesn't traverse filesystems.

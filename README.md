**gitrepocheck** check for git repositories and report all changes. It is
intended to run automatically to check for exemple git repository in /etc where
files can be changed by automated process like OS upgrades.

# Usage

Without any parameters, gitrepocheck search for git repositories recursively
from the current working directory.

With a pathname (-p path), gitrepocheck check for git repositories recusively
from this path.

Sometimes, one want to exclude a path from reporting. This can be achieved with
the skip option (-s path).

gitrepocheck doesn't traverse filesystems.

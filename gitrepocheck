#!/bin/bash

# 'gitRepoCheck'. Check GIT repositories for changed stuff.
# Copyright © 2015 Mathias Bocquet <mbocquet@sekoya.org>

if [ $# -lt 1 ]
then
    PATHTOCHECK=""
else
    PATHTOCHECK="$1"
fi

# Create a temporary file with this script as prefix
TMPFILE="$(tempfile -p $(basename $0))"

for REPOSITORY in $(find ${PATHTOCHECK} -xdev -type d -iname .git)
do
    # Strip '/.git' part of the REPOSITORY
    DIR=$(echo ${REPOSITORY}|sed 's;/.git;;')
    cd ${DIR}
    git status > ${TMPFILE}
    # if git status report nothing to commit, it looks like these two following
    # lines :
    # On branch master
    # nothing to commit, working directory clean
    # So if the last sentence, is not found, print the git status output
    if ! grep -q "nothing to commit.*working.*clean" ${TMPFILE}
    then
        printf "GIT repository at ${HOSTNAME}:${DIR} has changed\n"
        cat ${TMPFILE}
    fi
    cd - >/dev/null
    # Blank the temporary file
    >${TMPFILE}
done

rm ${TMPFILE}

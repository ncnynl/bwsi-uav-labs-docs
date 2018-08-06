Just some thoughts here, we could probably create scripts for most of these. Feel free to add and modify:

## Starting up drone for the day (while connected via SSH)

1. Startup script will update all software and pull the contents of `laboratory`, `documents`, and `aero_control` from `origin` (hopefully!)
2. Pull from `upstream` for any repo, as necessary
3. If there are merge conflicts:
    1. Resolve the merge conflicts manually
    2. Commit locally on the drone
    3. Push to `origin`


## Before shutting down drone for the day (while connected via SSH)

1. Commit `laboratory`, `documents`, and `aero_control` locally (if you made changes)
2. Pull from `upstream` for all repos and resolve any merge conflicts
3. Pull from `origin` for all repos and resolve any merge conflicts
4. Commit again
5. Push to `origin`

## Before working on personal computers

1. Commit locally
2. Pull from `upstream`, as necessary
3. Resolve  merge conflicts and commit
4. Follow the same steps for before shutting down the drone
5. Pull from `origin`
6. Resolve merge conflicts and commit
7. Push to `origin`

## After working on personal computers

1. Follow the same steps as before shutting down the drone

## Best Practices

* Create a `develop` branch in `aero_control` for any code written on local computers, before going into deployment?
* Commit often! (after making any minor, complete change)
  * Ensure the code can compile before pushing
* Use the imperative mood (action words, e.g. "Make changes to XYZ," "Add file for XYZ," "Implement XYZ") in commits. 

## Resources

* [Article on naming commits](https://chris.beams.io/posts/git-commit/)
* [Cool git cheatsheet](https://education.github.com/git-cheat-sheet-education.pdf)
* [Markdown cheatsheet (for `.md` files)](https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf)


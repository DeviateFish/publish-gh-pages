# publish-gh-pages

A set of simple scripts to enable publishing a production build of a page to
a `gh-pages` or `master` branch in your repository.

Note: this project currently assumes a node-based project (e.g. React, Polymer, etc),
and that your production build output directory is included in your `.gitignore` file.

## Usage:

Depending on your setup, you'll likely either be publishing to a `gh-pages` branch,
for project pages, or a `master` branch of user/organization GitHub pages.

* If you are publishing to your `master` branch, use `publish-master`.
* If you are publishing to your `gh-pages` branch, use `publish-gh-pages`.

## How it works:

The scripts are pretty straightforward: they check out your `master` or `gh-pages`
branch, and add a temporary `.gitignore` to exclude non-build files.  Then, it
copies the contents of your build's output directory into the root directory
of the branch.  It then adds all files not included in the `.gitignore` to the
branch, commits, and pushes the changes to github.  Then, it checks out the
branch it was on prior to checking out `master` or `gh-pages`.

## Future improvements:

In the future, I'll likely parameterize these things better, and maybe steal
the `.gitignore` from the development branch for use in the published branch.

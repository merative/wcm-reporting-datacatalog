# Introduction

The purpose of this site is to describe WCM Reporting and its sub-projects in a presentable, organised, and easy-to-use manner.

This site is powered by **[Docsify](https://docsify.js.org)**.

# Install Documentation tooling

Ensure your local environment has the Docusaurus dependancy installed. To install, run the following commands; the dependancies are only required to be install once.
```bash
npm i docsify-cli -g
```

# Install Documentation tooling

To clone the repository and to serve the docs site locally perform the following commands. Also, see **[docsify cli](https://github.com/docsifyjs/docsify-cli)** for command line options for Docsify.

```sh
git clone https://github.ibm.com/WH-GovHHS/wcm-reporting-docs.git
cd wcm-reporting-developer-docs
docsify serve ./docs  --open  -p3000
```
Load the example site at http://localhost:3000/ if it did not already open automatically. If port 3000 has already been taken, another port will be used. Look at the console messages to see which.

You should see the example site loaded in your web browser. There's also a LiveReload server running and any changes made to the docs and files in the website directory will cause the page to refresh.


# Contributing
When modifying developer documentation it is recommended to clone the **[wcm-reporting-docs](https://github.ibm.com/WH-GovHHS/wcm-reporting-docs)** repository, perform the changes, deploy the book locally to make sure it renders as expected.  Once everything is fine then perform a push to master.  


```sh
git clone https://github.ibm.com/WH-GovHHS/wcm-reporting-docs.git

git checkout -b branch_name_HERE
git add .
git status
git commit -m “add cognos documentation”
# fetches latest of all branches, but doesn't touch working tree
git fetch
# rebase current branch to latest master to get changes by others (so you do not overwrite)
git rebase origin/master
# then deliver your branch
git push origin cognosintegration

# now go to GitHub and create a Pull Request

```

# Pipeline

The content of the wiki can be found in the Git repo **[wcm-reporting-docs](https://github.ibm.com/WH-GovHHS/wcm-reporting-docs)**. The repo will shortly be polled by a [Travis Job](travis.ibm.com/) that will build and push the latest changes to GitHub Pages. The job can be triggered manually if needed.

# Authors
* Anthony Farrell
* Valerie Stafford
* John Rogers

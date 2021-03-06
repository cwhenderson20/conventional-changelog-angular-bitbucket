<!--[CN_HEADING]-->
# Contributing

Welcome! This document explains how you can contribute to making **conventional-changelog-angular-bitbucket** even better.


<!--[]-->

<!--[CN_GETTING_STARTED]-->
# Getting Started

## Installation

```
git clone <this repo>
npm install -g commitizen
npm install -g semantic-release-cli
npm install
```


<!--[]-->

<!--[RM_DIR_STRUCTURE]-->
## Directory Structure

Code is organised into modules which contain one-or-more components. This a great way to ensure maintainable code by encapsulation of behavior logic. A component is basically a self contained app usually in a single file or a folder with each concern as a file: style, template, specs, e2e, and component class. Here's how it looks:
```
conventional-changelog-angular-bitbucket/
 ├──config/                       * configuration files live here (e.g. eslint, verify, testUnit)
 │
 ├──src/                          * source code files should be here
 │
 ├──dist/                         * production-build code should live here
 │
 ├──reports/                      * test reports appear here
 │
 ├──test/                         * unit test specifications live here
 │
 ├──confit.yml                    * the project config file generated by 'yo confit'
 ├──CONTRIBUTING.md               * how to contribute to the project
 ├──README.md                     * this file
 └──package.json                  * NPM package description file
```


<!--[]-->

<!--[CN_GITFLOW_PROCESS]-->
# GitFlow Development Process

This project uses the [GitHub Flow](https://guides.github.com/introduction/flow/index.html) workflow.

## Create a branch
When you're working on a project, you're going to have a bunch of different features or ideas in progress at any given time – some of which are ready to go, and others which are not. Branching exists to help you manage this workflow.

When you create a branch in your project, you're creating an environment where you can try out new ideas. Changes you make on a branch don't affect the `master` branch, so you're free to experiment and commit changes, safe in the knowledge that your branch won't be merged until it's ready to be reviewed by someone you're collaborating with.

###ProTip

Branching is a core concept in Git, and the entire GitHub Flow is based upon it. There's only one rule: anything in the `master` branch is always deployable.

Because of this, it's extremely important that your new branch is created off of `master` when working on a feature or a fix. Your branch name should be descriptive (e.g., `refactor-authentication`, `user-content-cache-key`, `make-retina-avatars`), so that others can see what is being worked on.

## Add commits
Once your branch has been created, it's time to start making changes. Whenever you add, edit, or delete a file, you're making a commit, and adding them to your branch. This process of adding commits keeps track of your progress as you work on a feature branch.

Commits also create a transparent history of your work that others can follow to understand what you've done and why. Each commit has an associated commit message, which is a description explaining why a particular change was made. Furthermore, each commit is considered a separate unit of change. This lets you roll back changes if a bug is found, or if you decide to head in a different direction.

###ProTip

Commit messages are important, especially since Git tracks your changes and then displays them as commits once they're pushed to the server. By writing clear commit messages, you can make it easier for other people to follow along and provide feedback.

## Open a pull request

Pull Requests initiate discussion about your commits. Because they're tightly integrated with the underlying Git repository, anyone can see exactly what changes would be merged if they accept your request.

You can open a Pull Request at any point during the development process: when you have little or no code but want to share some screenshots or general ideas, when you're stuck and need help or advice, or when you're ready for someone to review your work. By using GitHub's @mention system in your Pull Request message, you can ask for feedback from specific people or teams, whether they're down the hall or ten time zones away.

###ProTip

Pull Requests are useful for contributing to open source projects and for managing changes to shared repositories. If you're using a Fork & Pull Model, Pull Requests provide a way to notify project maintainers about the changes you'd like them to consider. If you're using a Shared Repository Model, Pull Requests help start code review and conversation about proposed changes before they're merged into the `master` branch.

## Discuss and review your code
Once a Pull Request has been opened, the person or team reviewing your changes may have questions or comments. Perhaps the coding style doesn't match project guidelines, the change is missing unit tests, or maybe everything looks great and props are in order. Pull Requests are designed to encourage and capture this type of conversation.

You can also continue to push to your branch in light of discussion and feedback about your commits. If someone comments that you forgot to do something or if there is a bug in the code, you can fix it in your branch and push up the change. GitHub will show your new commits and any additional feedback you may receive in the unified Pull Request view.

###ProTip

Pull Request comments are written in Markdown, so you can embed images and emoji, use pre-formatted text blocks, and other lightweight formatting.

## Merge to `master`

Once your PR has passed any the integration tests and received approval to merge, it is time to merge your code into the `master` branch.

Once merged, Pull Requests preserve a record of the historical changes to your code. Because they're searchable, they let anyone go back in time to understand why and how a decision was made.

###ProTip

By incorporating certain keywords into the text of your Pull Request, you can associate issues with code. When your Pull Request is merged, the related issues are also closed. For example, entering the phrase Closes #32 would close issue number 32 in the repository. For more information, check out our help article.


<!--[]-->

<!--[CN_BUILD_TASKS]-->
## Build Tasks

Command | Description
:------ | :----------
<pre>npm run build</pre> | Generate production build into [dist/](dist/) folder
<pre>npm run dev</pre> | Run project in development mode (verify code, and re-verify when code is changed)
<pre>npm start</pre> | Alias for `npm run dev` task



<!--[]-->

<!--[CN_TEST_TASKS]-->
## Test Tasks

Command | Description
:------ | :----------
<pre>npm test</pre> | Alias for `npm run test:unit` task
<pre>npm run test:coverage</pre> | Run instrumented unit tests then verify coverage meets defined thresholds<ul><li>Returns non-zero exit code when coverage does not meet thresholds (as defined in istanbul.js)</li></ul>
<pre>npm run test:unit</pre> | Run unit tests whenever JS source or tests change<ul><li>Uses Mocha</li><li>Code coverage</li><li>Runs continuously (best to run in a separate window)</li></ul>
<pre>npm run test:unit:once</pre> | Run unit tests once<ul><li>Uses Mocha</li><li>Code coverage</li></ul>



<!--[]-->

<!--[CN_VERIFY_TASKS]-->
## Verification (Linting) Tasks

Command | Description
:------ | :----------
<pre>npm run verify</pre> | Verify code style and syntax<ul><li>Verifies source *and test code* aginst customisable rules (unlike Webpack loaders)</li></ul>
<pre>npm run verify:js</pre> | Verify Javascript code style and syntax
<pre>npm run verify:js:fix</pre> | Verify Javascript code style and syntax and fix any errors that can be fixed automatically
<pre>npm run verify:js:watch</pre> | Verify Javascript code style and syntax and watch files for changes
<pre>npm run verify:watch</pre> | Runs verify task whenever JS or CSS code is changed



<!--[]-->

<!--[CN_COMMIT_TASKS]-->
## Commit Tasks

Command | Description
:------ | :----------
<pre>git status</pre> | Lists the current branch and the status of changed files
<pre>git log</pre> | Displays the commit log (press Q to quit viewing)
<pre>git add .</pre> | Stages all modified & untracked files, ready to be committed
<pre>git cz</pre> | Commit changes to local repository using Commitizen<ul><li>Asks questions about the change to generate a valid conventional commit message</li><li>Can be customised by modifying [config/release/commitMessageConfig.js](config/release/commitMessageConfig.js)</li></ul>
<pre>git push</pre> | Push local repository changes to remote repository


<!--[]-->

<!--[CN_DOCUMENTATION_TASKS]-->



<!--[]-->

<!--[CN_RELEASE_TASKS]-->
## Release Tasks

Command | Description
:------ | :----------
<pre>npm run pre-release</pre> | Verify code, run unit tests, check test coverage, build software. This task is designed to be run before
the `semantic-release` task.
<ul><li>Run `semantic-release-cli setup` once you have a remote repository. See https://github.com/semantic-release/cli for details.</li><li>Semantic-release integrates with Travis CI (or similar tools) to generate release notes
for each release (which appears in the "Releases" section in GitHub) and
publishes the package to NPM (when all the tests are successful) with a semantic version number.
</li></ul>
<pre>npm run upload-coverage</pre> | Uploads code-coverage metrics to Coveralls.io<ul><li>Setup - https://coveralls.zendesk.com/hc/en-us/articles/201347419-Coveralls-currently-supports</li><li>Define an environment variable called COVERALLS_REPO_TOKEN in your build environment with the repo token from https://coveralls.io/github/<repo-name>/settings</li></ul>



<!--[]-->


<!--[CN_CHANGING_BUILD_TOOL_CONFIG]-->
## Changing build-tool configuration

There are 3 ways you can change the build-tool configuration for this project:

1. BEST: Modify the Confit configuration file ([confit.yml](confit.yml)) by hand, then re-run `yo confit` and tell it to use the existing configuration.
1. OK: Re-run `yo confit` and provide new answers to the questions. **Confit will attempt to overwrite your existing configuration (it will prompt for confirmation), so make sure you have committed your code to a source control (e.g. git) first**.
  There are certain configuration settings which can **only** be specified by hand, in which case the first approach is still best.
1. RISKY: Modify the generated build-tool config by hand. Be aware that if you re-run `yo confit` it will attempt to overwrite your changes. So commit your changes to source control first.

Additionally, the **currently-generated** configuration can be extended in the following ways:

- The task configuration is defined in [package.json](package.json). It is possible to change the task definitions to add your own sub-tasks.
You can also use the `pre...` and `post...` script-name prefixes to run commands before (pre) and after (post) the generated commands.

- The `entryPoint.entryPoints` string in [confit.yml](confit.yml) is designed to be edited manually. It represents the starting-point(s) of the application (like a `main()` function). A NodeJS application has one entry point. E.g. `src/index.js`




<!--[]-->




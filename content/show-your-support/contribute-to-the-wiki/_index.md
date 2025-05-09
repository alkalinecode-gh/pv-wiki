# Contribute to the Wiki

The PureVanilla wiki is a [Hugo](https://gohugo.io/) site deployed using [Cloudflare Pages](https://pages.cloudflare.com/) and its source is hosted openly at [our GitHub repository](https://github.com/purevanillaco/wiki).

To contribute to the Wiki, you will need a [GitHub](https://github.com/signup) account. Once you have created yours using the link, proceed with the steps below.

1. Install `git`
	* [→ Download here](https://git-scm.com/downloads) (Note: If you are using macOS, using homebrew is recommended. If you are using Linux, search your distributions package manager first.)
2. Install the GitHub CLI
	* [→ Installation instructions](https://github.com/cli/cli#installation)
3. Log into your GitHub account in the GitHub CLI.
	1. Open the terminal on your OS.
		* **On Windows:** Press `Windows+R` and enter `cmd`. Press the return key.
		* **On macOS:** In Spotlight (`Cmd+Space`), search for Terminal and open.
		* **On Linux:** Most distributions bundle a Terminal emulator. Use the search functionality of your Desktop environment to search for "Terminal".
	2. Type `gh auth login` and Enter. If `gh` is not found, you may need to log out and back in or restart your computer to finalize the installation of the GitHub CLI.
	3. Follow the steps in your terminal.
4. Fork and clone our GitHub repository by running `gh repo fork purevanillaco/wiki --fork-name pv-wiki --clone`.
5. Move into the cloned repository by running `cd pv-wiki`.
6. Create a new branch with a name that is descriptive of the changes you plan to make. Run `git checkout -b <branch-name>`.
7. Install Hugo server.
	* [→ Installation instructions](https://gohugo.io/installation/)
8. You are now ready to make changes! If you are new to using `git`, [this may be helpful to you](https://docs.github.com/en/get-started/using-git/about-git#basic-git-commands). The entirety of the wiki is written in American English. Please make sure your contribution aligns with this. You can find the Markdown source files for the wiki in the `content/` subdirectory. Also make sure to take a look at the [commit style guide](#commits).
9. Once you are done making changes, you can test them locally by running `hugo server` in the root folder of the repository (`pv-wiki`). The page will be built and hosted locally on your machine. Use your web browser to navigate to the address given by Hugo inside your terminal. If building the page fails, you may need to install Go first.
	* [→ Installation instructions for Go](https://go.dev/doc/install)
10. Sync your changes to your fork of the PureVanilla wiki by running `git push`. If it is your first time pushing from a new branch, do `git push -u origin <branch-name>`.
11. Finally, create a pull request by navigating to the website of your GitHub repository `https://github.com/<your-username>/pv-wiki/`, select the branch you worked on, and click "Contribute". You can now open a pull request that describes your changes, which will later be reviewed and, if everything is in order, merged into the real, official, PureVanilla wiki!
12. Thanks for contributing!

## Commits
Commits are a milestone along the path of making changes to a codebase. Good commits are **atomic** and **descriptive**.

### Atomicity
An atomic commit is one which makes exactly **one** change. We know it's not always easy, but try to do this when contributing! It keeps things tidy and can make the review of your pull request faster!

**An example**

_instead of..._

`wiki: Add new article and another new article`
```
+ # New article
+ 
+ Your inspiring words

+ # Another new article
+ 
+ More inspiring words
```

_better:_

`wiki: Add new article`
```md
+ # New article
+ 
+ Your inspiring words
```
`wiki: Add another new article`
```md
+ # Another new article
+ 
+ More inspiring words
```

### Descriptivity

Your commit message is your commits personality. It should give a good idea of what you changed, and do so concisely.

**An example**

* _bad:_ `git commit -m "Changed chill article"`
* _better:_ `git commit -m "Added chill2 instance"`


Sometimes, even atomic commits can be big, and we appreciate the time you put into them! That being said, remember that your commit message is something most people will only scan over and not read in its entirety, and it should still convey what you changed well enough. To achieve this, keep the first line of your commit message to 80 characters at most! If you absolutely need to convey more information than that, use multiple lines for your commit message.

```
A short description of the change

A detailed description of every little thing you changed, modified, improved and did to achieve what you set out to achieve!
```

**An example**

* _bad:_ `git commit -m "Added the world download and seed information to chill and cool as well as the simply world downloads for the maps before the reset"`
* _better:_ `git commit -m "Add info for pre-reset maps"`

Not all commits are the same. A change to how the site is fundamentally rendered should not blend in with a bunch of spelling mistake corrections. To distinguish between commits, we use a system called [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/). To sum it up, all your commit messages will look like this:

```
type: Short description

A detailed description of every little thing you changed, modified, improved and did to achieve what you set out to achieve!
```

Where `type:` lets us classify commits in different ways. We use the following types:

* `wiki`: A change to an article.
* `index`: A change/addition of a page that merely points to other pages and contains no information in and of itself.
* `language`: Fixing a spelling or grammar mistake, or improving phrasing.
* `page`: A change to how the underlying page works.
* `workspace`: A change to the workspace.

> **Note:** This list of types is not exhaustive, and will probably fall short at some point in the future. You may use other types than are listed here. When you invent a new type which will likely be used in subsequent commits, please add it to this list so we can avoid a sprawl of loosely defined commit types.

Another thing to note about Conventional Commits is that after `type`, parentheses `(specifier)` may be used to make the commit message more specific, or an exlamation mark `!` to indicate a breaking change (which should be exceedingly rare for a wiki, but it's worth mentioning nonetheless).

**One last example**

This is what a good commit message might look like:

```
wiki(simply1): Add information about old map

Added a download link and additional information about the simply1 map that reset on <date> as well as moving the seed information to the dedicated history section.
```

> **Note:** Don't stress too hard over this, often just having read this once and keeping it in the back of your mind will help you write a good commit message; you do not need to fit every single criterion of this guide perfectly.
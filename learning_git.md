

# First Time Setup

## Git Config (Defaults)

- user.email=aryans.vinay@gmail.com
- user.name=Vinay Aggarwal
- core.repositoryformatversion=0
- core.filemode=true
- core.bare=false
- core.logallrefupdates=true


## Git Config
 - core.editor=subl
 - color.diff=auto
 - color.status=auto
 - color.branch=auto
 - color.interactive=auto
 - color.diff=auto

## Setup Meld as a diff tool (Not Required if you are using a git gui tool)

 [Meld as diff Tool](https://nathanhoad.net/how-to-meld-for-git-diffs-in-ubuntu-hardy)


## Git Status

	$ git status -s
	 M README
	MM Rakefile
	A  lib/git.rb
	M  lib/simplegit.rb
	?? LICENSE.txt

## Ignoring a file

 - Blank lines or lines starting with # are ignored.
 - Standard glob patterns work.
 - You can end patterns with a forward slash (/) to specify a directory.
 - You can negate a pattern by starting it with an exclamation point (!).

Glob patterns are like simplified regular expressions that shells use. An asterisk (*) matches zero or more characters; [abc] matches any character inside the brackets (in this case a, b, or c); a question mark (?) matches a single character; and brackets enclosing characters separated by a hyphen([0-9]) matches any character between them (in this case 0 through 9). You can also use two asterisks to match nested directories; a/**/z would match a/z, a/b/z, a/b/c/z, and so on.

### no .a files
*.a

### but do track lib.a, even though you're ignoring .a files above
!lib.a

### only ignore the root TODO file, not subdir/TODO
/TODO

### ignore all files in the build/ directory
build/

### ignore doc/notes.txt, but not doc/server/arch.txt
doc/*.txt

### ignore all .txt files in the doc/ directory
doc/**/*.txt


# Git Diff

 - `git diff` # only unstaged
 - `git diff --staged` # only staged
 - `git diff --cached` # synonym of --staged


# Git Commit

 - `git commit -m "commit message"`
 - `git commit -a -m "commit message"` # skip staging and add/commit everything tracked


# Git Remove

 - `git rm filename.md`
 - `git rm --cached filename.md` # remove from git but not from directory
 - `git rm log/\*.log` # Pass patterns

Note the backslash ( \ ) in front of the *. This is necessary because Git does its own filename expansion in addition to your shell’s filename expansion. This command removes all files that have the .log extension in the log/ directory. Or, you can do something like this:

# Git Move

 - `git mv`


# Git Log

 - `git log`
 - `git log -3` # limit 3
 - `git log -p` # show diff as well
 - `git log --author vinay`
 - `git log --stat # Show the stat (no of lines changed)
 - `git log --pretty=format:"%h - %an, %ar : %s"`

 - `git log --since`


	$ git log -S "core.editor"
	commit 5ea9fa63d0d5522a0ffdfc08ee2a6fbf93e69c0e
	Author: Vinay Aggarwal <aryans.vinay@gmail.com>
	Date:   Wed May 13 20:31:54 2015 +0530

	    Learning core.editor setting

Few Other switches are --since, --after, --until, --before, --author, --committer, --grep, -S

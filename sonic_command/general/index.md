[上一頁](https://jian-hong-wu.github.io/blog/sonic_command/)

### General commands
* [$ help](https://jian-hong-wu.github.io/blog/sonic_command/general/#-help)
* [$ cd](https://jian-hong-wu.github.io/blog/sonic_command/general/#-cd)
* [$ mkdir](https://jian-hong-wu.github.io/blog/sonic_command/general/#-mkdir)
* [$ rmdir](https://jian-hong-wu.github.io/blog/sonic_command/general/#-rmdir)
* [$ ls](https://jian-hong-wu.github.io/blog/sonic_command/general/#-ls)
* [$ dir](https://jian-hong-wu.github.io/blog/sonic_command/general/#-dir)
* [$ rm](https://jian-hong-wu.github.io/blog/sonic_command/general/#-rm)
* [$ cat](https://jian-hong-wu.github.io/blog/sonic_command/general/#-cat)
* [$ export](https://jian-hong-wu.github.io/blog/sonic_command/general/#-export)
* [$ vi](https://jian-hong-wu.github.io/blog/sonic_command/general/#-vi)
* [$ history](https://jian-hong-wu.github.io/blog/sonic_command/general/#-history)
* [$ date](https://jian-hong-wu.github.io/blog/sonic_command/general/#-date)
* [$ export](https://jian-hong-wu.github.io/blog/sonic_command/general/#-export)
* [$ pwd](https://jian-hong-wu.github.io/blog/sonic_command/general/#-pwd)
* [$ logout](https://jian-hong-wu.github.io/blog/sonic_command/general/#-logout)

$ help
---
<pre>admin@sonic:~$ help
GNU bash, version 5.0.3(1)-release (x86_64-pc-linux-gnu)
These shell commands are defined internally.  Type `help&apos; to see this list.
Type `help name&apos; to find out more about the function `name&apos;.
Use `info bash&apos; to find out more about the shell in general.
Use `man -k&apos; or `info&apos; to find out more about commands not in this list.

A star (*) next to a name means that the command is disabled.

 job_spec [&amp;]                            history [-c] [-d offset] [n] or hist&gt;
 (( expression ))                        if COMMANDS; then COMMANDS; [ elif C&gt;
 . filename [arguments]                  jobs [-lnprs] [jobspec ...] or jobs &gt;
 :                                       kill [-s sigspec | -n signum | -sigs&gt;
 [ arg... ]                              let arg [arg ...]
 [[ expression ]]                        local [option] name[=value] ...
 alias [-p] [name[=value] ... ]          logout [n]
 bg [job_spec ...]                       mapfile [-d delim] [-n count] [-O or&gt;
 bind [-lpsvPSVX] [-m keymap] [-f file&gt;  popd [-n] [+N | -N]
 break [n]                               printf [-v var] format [arguments]
 builtin [shell-builtin [arg ...]]       pushd [-n] [+N | -N | dir]
 caller [expr]                           pwd [-LP]
 case WORD in [PATTERN [| PATTERN]...)&gt;  read [-ers] [-a array] [-d delim] [-&gt;
 cd [-L|[-P [-e]] [-@]] [dir]            readarray [-d delim] [-n count] [-O &gt;
 command [-pVv] command [arg ...]        readonly [-aAf] [name[=value] ...] o&gt;
 compgen [-abcdefgjksuv] [-o option] [&gt;  return [n]
 complete [-abcdefgjksuv] [-pr] [-DEI]&gt;  select NAME [in WORDS ... ;] do COMM&gt;
 compopt [-o|+o option] [-DEI] [name .&gt;  set [-abefhkmnptuvxBCHP] [-o option-&gt;
 continue [n]                            shift [n]
 coproc [NAME] command [redirections]    shopt [-pqsu] [-o] [optname ...]
 declare [-aAfFgilnrtux] [-p] [name[=v&gt;  source filename [arguments]
 dirs [-clpv] [+N] [-N]                  suspend [-f]
 disown [-h] [-ar] [jobspec ... | pid &gt;  test [expr]
 echo [-neE] [arg ...]                   time [-p] pipeline
 enable [-a] [-dnps] [-f filename] [na&gt;  times
 eval [arg ...]                          trap [-lp] [[arg] signal_spec ...]
 exec [-cl] [-a name] [command [argume&gt;  true
 exit [n]                                type [-afptP] name [name ...]
 export [-fn] [name[=value] ...] or ex&gt;  typeset [-aAfFgilnrtux] [-p] name[=v&gt;
 false                                   ulimit [-SHabcdefiklmnpqrstuvxPT] [l&gt;
 fc [-e ename] [-lnr] [first] [last] o&gt;  umask [-p] [-S] [mode]
 fg [job_spec]                           unalias [-a] name [name ...]
 for NAME [in WORDS ... ] ; do COMMAND&gt;  unset [-f] [-v] [-n] [name ...]
 for (( exp1; exp2; exp3 )); do COMMAN&gt;  until COMMANDS; do COMMANDS; done
 function name { COMMANDS ; } or name &gt;  variables - Names and meanings of so&gt;
 getopts optstring name [arg]            wait [-fn] [id ...]
 hash [-lr] [-p pathname] [-dt] [name &gt;  while COMMANDS; do COMMANDS; done
 help [-dms] [pattern ...]               { COMMANDS ; }
admin@sonic:~$ 
</pre>
---

$ cd
---
<pre>admin@sonic:~$ cd --help
cd: cd [-L|[-P [-e]] [-@]] [dir]
    Change the shell working directory.
    
    Change the current directory to DIR.  The default DIR is the value of the
    HOME shell variable.
    
    The variable CDPATH defines the search path for the directory containing
    DIR.  Alternative directory names in CDPATH are separated by a colon (:).
    A null directory name is the same as the current directory.  If DIR begins
    with a slash (/), then CDPATH is not used.
    
    If the directory is not found, and the shell option `cdable_vars&apos; is set,
    the word is assumed to be  a variable name.  If that variable has a value,
    its value is used for DIR.
    
    Options:
      -L	force symbolic links to be followed: resolve symbolic
    		links in DIR after processing instances of `..&apos;
      -P	use the physical directory structure without following
    		symbolic links: resolve symbolic links in DIR before
    		processing instances of `..&apos;
      -e	if the -P option is supplied, and the current working
    		directory cannot be determined successfully, exit with
    		a non-zero status
      -@	on systems that support it, present a file with extended
    		attributes as a directory containing the file attributes
    
    The default is to follow symbolic links, as if `-L&apos; were specified.
    `..&apos; is processed by removing the immediately previous pathname component
    back to a slash or the beginning of DIR.
    
    Exit Status:
    Returns 0 if the directory is changed, and if $PWD is set successfully when
    -P is used; non-zero otherwise.
admin@sonic:~$ 
</pre>
---

$ mkdir
---
<pre>admin@sonic:~$ mkdir --help
Usage: mkdir [OPTION]... DIRECTORY...
Create the DIRECTORY(ies), if they do not already exist.

Mandatory arguments to long options are mandatory for short options too.
  -m, --mode=MODE   set file mode (as in chmod), not a=rwx - umask
  -p, --parents     no error if existing, make parent directories as needed
  -v, --verbose     print a message for each created directory
  -Z                   set SELinux security context of each created directory
                         to the default type
      --context[=CTX]  like -Z, or if CTX is specified then set the SELinux
                         or SMACK security context to CTX
      --help     display this help and exit
      --version  output version information and exit

GNU coreutils online help: &lt;https://www.gnu.org/software/coreutils/&gt;
Full documentation at: &lt;https://www.gnu.org/software/coreutils/mkdir&gt;
or available locally via: info &apos;(coreutils) mkdir invocation&apos;
admin@sonic:~$ 
</pre>
---

$ rmdir
---
<pre>admin@sonic:~$ rmdir --help
Usage: rmdir [OPTION]... DIRECTORY...
Remove the DIRECTORY(ies), if they are empty.

      --ignore-fail-on-non-empty
                  ignore each failure that is solely because a directory
                    is non-empty
  -p, --parents   remove DIRECTORY and its ancestors; e.g., &apos;rmdir -p a/b/c&apos; is
                    similar to &apos;rmdir a/b/c a/b a&apos;
  -v, --verbose   output a diagnostic for every directory processed
      --help     display this help and exit
      --version  output version information and exit

GNU coreutils online help: &lt;https://www.gnu.org/software/coreutils/&gt;
Full documentation at: &lt;https://www.gnu.org/software/coreutils/rmdir&gt;
or available locally via: info &apos;(coreutils) rmdir invocation&apos;
admin@sonic:~$ 
</pre>
---

$ ls
---
<pre>admin@sonic:~$ ls --help
Usage: ls [OPTION]... [FILE]...
List information about the FILEs (the current directory by default).
Sort entries alphabetically if none of -cftuvSUX nor --sort is specified.

Mandatory arguments to long options are mandatory for short options too.
  -a, --all                  do not ignore entries starting with .
  -A, --almost-all           do not list implied . and ..
      --author               with -l, print the author of each file
  -b, --escape               print C-style escapes for nongraphic characters
      --block-size=SIZE      with -l, scale sizes by SIZE when printing them;
                               e.g., &apos;--block-size=M&apos;; see SIZE format below
  -B, --ignore-backups       do not list implied entries ending with ~
  -c                         with -lt: sort by, and show, ctime (time of last
                               modification of file status information);
                               with -l: show ctime and sort by name;
                               otherwise: sort by ctime, newest first
  -C                         list entries by columns
      --color[=WHEN]         colorize the output; WHEN can be &apos;always&apos; (default
                               if omitted), &apos;auto&apos;, or &apos;never&apos;; more info below
  -d, --directory            list directories themselves, not their contents
  -D, --dired                generate output designed for Emacs&apos; dired mode
  -f                         do not sort, enable -aU, disable -ls --color
  -F, --classify             append indicator (one of */=&gt;@|) to entries
      --file-type            likewise, except do not append &apos;*&apos;
      --format=WORD          across -x, commas -m, horizontal -x, long -l,
                               single-column -1, verbose -l, vertical -C
      --full-time            like -l --time-style=full-iso
  -g                         like -l, but do not list owner
      --group-directories-first
                             group directories before files;
                               can be augmented with a --sort option, but any
                               use of --sort=none (-U) disables grouping
  -G, --no-group             in a long listing, don&apos;t print group names
  -h, --human-readable       with -l and -s, print sizes like 1K 234M 2G etc.
      --si                   likewise, but use powers of 1000 not 1024
  -H, --dereference-command-line
                             follow symbolic links listed on the command line
      --dereference-command-line-symlink-to-dir
                             follow each command line symbolic link
                               that points to a directory
      --hide=PATTERN         do not list implied entries matching shell PATTERN
                               (overridden by -a or -A)
      --hyperlink[=WHEN]     hyperlink file names; WHEN can be &apos;always&apos;
                               (default if omitted), &apos;auto&apos;, or &apos;never&apos;
      --indicator-style=WORD  append indicator with style WORD to entry names:
                               none (default), slash (-p),
                               file-type (--file-type), classify (-F)
  -i, --inode                print the index number of each file
  -I, --ignore=PATTERN       do not list implied entries matching shell PATTERN
  -k, --kibibytes            default to 1024-byte blocks for disk usage;
                               used only with -s and per directory totals
  -l                         use a long listing format
  -L, --dereference          when showing file information for a symbolic
                               link, show information for the file the link
                               references rather than for the link itself
  -m                         fill width with a comma separated list of entries
  -n, --numeric-uid-gid      like -l, but list numeric user and group IDs
  -N, --literal              print entry names without quoting
  -o                         like -l, but do not list group information
  -p, --indicator-style=slash
                             append / indicator to directories
  -q, --hide-control-chars   print ? instead of nongraphic characters
      --show-control-chars   show nongraphic characters as-is (the default,
                               unless program is &apos;ls&apos; and output is a terminal)
  -Q, --quote-name           enclose entry names in double quotes
      --quoting-style=WORD   use quoting style WORD for entry names:
                               literal, locale, shell, shell-always,
                               shell-escape, shell-escape-always, c, escape
                               (overrides QUOTING_STYLE environment variable)
  -r, --reverse              reverse order while sorting
  -R, --recursive            list subdirectories recursively
  -s, --size                 print the allocated size of each file, in blocks
  -S                         sort by file size, largest first
      --sort=WORD            sort by WORD instead of name: none (-U), size (-S),
                               time (-t), version (-v), extension (-X)
      --time=WORD            with -l, show time as WORD instead of default
                               modification time: atime or access or use (-u);
                               ctime or status (-c); also use specified time
                               as sort key if --sort=time (newest first)
      --time-style=TIME_STYLE  time/date format with -l; see TIME_STYLE below
  -t                         sort by modification time, newest first
  -T, --tabsize=COLS         assume tab stops at each COLS instead of 8
  -u                         with -lt: sort by, and show, access time;
                               with -l: show access time and sort by name;
                               otherwise: sort by access time, newest first
  -U                         do not sort; list entries in directory order
  -v                         natural sort of (version) numbers within text
  -w, --width=COLS           set output width to COLS.  0 means no limit
  -x                         list entries by lines instead of by columns
  -X                         sort alphabetically by entry extension
  -Z, --context              print any security context of each file
  -1                         list one file per line.  Avoid &apos;\n&apos; with -q or -b
      --help     display this help and exit
      --version  output version information and exit

The SIZE argument is an integer and optional unit (example: 10K is 10*1024).
Units are K,M,G,T,P,E,Z,Y (powers of 1024) or KB,MB,... (powers of 1000).

The TIME_STYLE argument can be full-iso, long-iso, iso, locale, or +FORMAT.
FORMAT is interpreted like in date(1).  If FORMAT is FORMAT1&lt;newline&gt;FORMAT2,
then FORMAT1 applies to non-recent files and FORMAT2 to recent files.
TIME_STYLE prefixed with &apos;posix-&apos; takes effect only outside the POSIX locale.
Also the TIME_STYLE environment variable sets the default style to use.

Using color to distinguish file types is disabled both by default and
with --color=never.  With --color=auto, ls emits color codes only when
standard output is connected to a terminal.  The LS_COLORS environment
variable can change the settings.  Use the dircolors command to set it.

Exit status:
 0  if OK,
 1  if minor problems (e.g., cannot access subdirectory),
 2  if serious trouble (e.g., cannot access command-line argument).

GNU coreutils online help: &lt;https://www.gnu.org/software/coreutils/&gt;
Full documentation at: &lt;https://www.gnu.org/software/coreutils/ls&gt;
or available locally via: info &apos;(coreutils) ls invocation&apos;
admin@sonic:~$ 
</pre>
---

$ dir
---
<pre>admin@sonic:~$ dir --help
Usage: dir [OPTION]... [FILE]...
List information about the FILEs (the current directory by default).
Sort entries alphabetically if none of -cftuvSUX nor --sort is specified.

Mandatory arguments to long options are mandatory for short options too.
  -a, --all                  do not ignore entries starting with .
  -A, --almost-all           do not list implied . and ..
      --author               with -l, print the author of each file
  -b, --escape               print C-style escapes for nongraphic characters
      --block-size=SIZE      with -l, scale sizes by SIZE when printing them;
                               e.g., &apos;--block-size=M&apos;; see SIZE format below
  -B, --ignore-backups       do not list implied entries ending with ~
  -c                         with -lt: sort by, and show, ctime (time of last
                               modification of file status information);
                               with -l: show ctime and sort by name;
                               otherwise: sort by ctime, newest first
  -C                         list entries by columns
      --color[=WHEN]         colorize the output; WHEN can be &apos;always&apos; (default
                               if omitted), &apos;auto&apos;, or &apos;never&apos;; more info below
  -d, --directory            list directories themselves, not their contents
  -D, --dired                generate output designed for Emacs&apos; dired mode
  -f                         do not sort, enable -aU, disable -ls --color
  -F, --classify             append indicator (one of */=&gt;@|) to entries
      --file-type            likewise, except do not append &apos;*&apos;
      --format=WORD          across -x, commas -m, horizontal -x, long -l,
                               single-column -1, verbose -l, vertical -C
      --full-time            like -l --time-style=full-iso
  -g                         like -l, but do not list owner
      --group-directories-first
                             group directories before files;
                               can be augmented with a --sort option, but any
                               use of --sort=none (-U) disables grouping
  -G, --no-group             in a long listing, don&apos;t print group names
  -h, --human-readable       with -l and -s, print sizes like 1K 234M 2G etc.
      --si                   likewise, but use powers of 1000 not 1024
  -H, --dereference-command-line
                             follow symbolic links listed on the command line
      --dereference-command-line-symlink-to-dir
                             follow each command line symbolic link
                               that points to a directory
      --hide=PATTERN         do not list implied entries matching shell PATTERN
                               (overridden by -a or -A)
      --hyperlink[=WHEN]     hyperlink file names; WHEN can be &apos;always&apos;
                               (default if omitted), &apos;auto&apos;, or &apos;never&apos;
      --indicator-style=WORD  append indicator with style WORD to entry names:
                               none (default), slash (-p),
                               file-type (--file-type), classify (-F)
  -i, --inode                print the index number of each file
  -I, --ignore=PATTERN       do not list implied entries matching shell PATTERN
  -k, --kibibytes            default to 1024-byte blocks for disk usage;
                               used only with -s and per directory totals
  -l                         use a long listing format
  -L, --dereference          when showing file information for a symbolic
                               link, show information for the file the link
                               references rather than for the link itself
  -m                         fill width with a comma separated list of entries
  -n, --numeric-uid-gid      like -l, but list numeric user and group IDs
  -N, --literal              print entry names without quoting
  -o                         like -l, but do not list group information
  -p, --indicator-style=slash
                             append / indicator to directories
  -q, --hide-control-chars   print ? instead of nongraphic characters
      --show-control-chars   show nongraphic characters as-is (the default,
                               unless program is &apos;ls&apos; and output is a terminal)
  -Q, --quote-name           enclose entry names in double quotes
      --quoting-style=WORD   use quoting style WORD for entry names:
                               literal, locale, shell, shell-always,
                               shell-escape, shell-escape-always, c, escape
                               (overrides QUOTING_STYLE environment variable)
  -r, --reverse              reverse order while sorting
  -R, --recursive            list subdirectories recursively
  -s, --size                 print the allocated size of each file, in blocks
  -S                         sort by file size, largest first
      --sort=WORD            sort by WORD instead of name: none (-U), size (-S),
                               time (-t), version (-v), extension (-X)
      --time=WORD            with -l, show time as WORD instead of default
                               modification time: atime or access or use (-u);
                               ctime or status (-c); also use specified time
                               as sort key if --sort=time (newest first)
      --time-style=TIME_STYLE  time/date format with -l; see TIME_STYLE below
  -t                         sort by modification time, newest first
  -T, --tabsize=COLS         assume tab stops at each COLS instead of 8
  -u                         with -lt: sort by, and show, access time;
                               with -l: show access time and sort by name;
                               otherwise: sort by access time, newest first
  -U                         do not sort; list entries in directory order
  -v                         natural sort of (version) numbers within text
  -w, --width=COLS           set output width to COLS.  0 means no limit
  -x                         list entries by lines instead of by columns
  -X                         sort alphabetically by entry extension
  -Z, --context              print any security context of each file
  -1                         list one file per line.  Avoid &apos;\n&apos; with -q or -b
      --help     display this help and exit
      --version  output version information and exit

The SIZE argument is an integer and optional unit (example: 10K is 10*1024).
Units are K,M,G,T,P,E,Z,Y (powers of 1024) or KB,MB,... (powers of 1000).

The TIME_STYLE argument can be full-iso, long-iso, iso, locale, or +FORMAT.
FORMAT is interpreted like in date(1).  If FORMAT is FORMAT1&lt;newline&gt;FORMAT2,
then FORMAT1 applies to non-recent files and FORMAT2 to recent files.
TIME_STYLE prefixed with &apos;posix-&apos; takes effect only outside the POSIX locale.
Also the TIME_STYLE environment variable sets the default style to use.

Using color to distinguish file types is disabled both by default and
with --color=never.  With --color=auto, ls emits color codes only when
standard output is connected to a terminal.  The LS_COLORS environment
variable can change the settings.  Use the dircolors command to set it.

Exit status:
 0  if OK,
 1  if minor problems (e.g., cannot access subdirectory),
 2  if serious trouble (e.g., cannot access command-line argument).

GNU coreutils online help: &lt;https://www.gnu.org/software/coreutils/&gt;
Full documentation at: &lt;https://www.gnu.org/software/coreutils/dir&gt;
or available locally via: info &apos;(coreutils) dir invocation&apos;
admin@sonic:~$ 
</pre>
---

$ rm
---
<pre>admin@sonic:~$ rm --help
Usage: rm [OPTION]... [FILE]...
Remove (unlink) the FILE(s).

  -f, --force           ignore nonexistent files and arguments, never prompt
  -i                    prompt before every removal
  -I                    prompt once before removing more than three files, or
                          when removing recursively; less intrusive than -i,
                          while still giving protection against most mistakes
      --interactive[=WHEN]  prompt according to WHEN: never, once (-I), or
                          always (-i); without WHEN, prompt always
      --one-file-system  when removing a hierarchy recursively, skip any
                          directory that is on a file system different from
                          that of the corresponding command line argument
      --no-preserve-root  do not treat &apos;/&apos; specially
      --preserve-root[=all]  do not remove &apos;/&apos; (default);
                              with &apos;all&apos;, reject any command line argument
                              on a separate device from its parent
  -r, -R, --recursive   remove directories and their contents recursively
  -d, --dir             remove empty directories
  -v, --verbose         explain what is being done
      --help     display this help and exit
      --version  output version information and exit

By default, rm does not remove directories.  Use the --recursive (-r or -R)
option to remove each listed directory, too, along with all of its contents.

To remove a file whose name starts with a &apos;-&apos;, for example &apos;-foo&apos;,
use one of these commands:
  rm -- -foo

  rm ./-foo

Note that if you use rm to remove a file, it might be possible to recover
some of its contents, given sufficient expertise and/or time.  For greater
assurance that the contents are truly unrecoverable, consider using shred.

GNU coreutils online help: &lt;https://www.gnu.org/software/coreutils/&gt;
Full documentation at: &lt;https://www.gnu.org/software/coreutils/rm&gt;
or available locally via: info &apos;(coreutils) rm invocation&apos;
admin@sonic:~$ 
</pre>
---

$ cat
---
<pre>admin@sonic:~$ cat --help
Usage: cat [OPTION]... [FILE]...
Concatenate FILE(s) to standard output.

With no FILE, or when FILE is -, read standard input.

  -A, --show-all           equivalent to -vET
  -b, --number-nonblank    number nonempty output lines, overrides -n
  -e                       equivalent to -vE
  -E, --show-ends          display $ at end of each line
  -n, --number             number all output lines
  -s, --squeeze-blank      suppress repeated empty output lines
  -t                       equivalent to -vT
  -T, --show-tabs          display TAB characters as ^I
  -u                       (ignored)
  -v, --show-nonprinting   use ^ and M- notation, except for LFD and TAB
      --help     display this help and exit
      --version  output version information and exit

Examples:
  cat f - g  Output f&apos;s contents, then standard input, then g&apos;s contents.
  cat        Copy standard input to standard output.

GNU coreutils online help: &lt;https://www.gnu.org/software/coreutils/&gt;
Full documentation at: &lt;https://www.gnu.org/software/coreutils/cat&gt;
or available locally via: info &apos;(coreutils) cat invocation&apos;
admin@sonic:~$ 
</pre>
---

$ export
---
<pre>admin@sonic:~$ export --help
export: export [-fn] [name[=value] ...] or export -p
    Set export attribute for shell variables.
    
    Marks each NAME for automatic export to the environment of subsequently
    executed commands.  If VALUE is supplied, assign VALUE before exporting.
    
    Options:
      -f	refer to shell functions
      -n	remove the export property from each NAME
      -p	display a list of all exported variables and functions
    
    An argument of `--&apos; disables further option processing.
    
    Exit Status:
    Returns success unless an invalid option is given or NAME is invalid.
admin@sonic:~$ 
</pre>
---

$ vi
---
<pre>admin@sonic:~$ vi --help
VIM - Vi IMproved 8.1 (2018 May 18, compiled Jun 15 2019 16:41:15)

Usage: vim [arguments] [file ..]       edit specified file(s)
   or: vim [arguments] -               read text from stdin
   or: vim [arguments] -t tag          edit file where tag is defined
   or: vim [arguments] -q [errorfile]  edit file with first error

Arguments:
   --			Only file names after this
   -v			Vi mode (like &quot;vi&quot;)
   -e			Ex mode (like &quot;ex&quot;)
   -E			Improved Ex mode
   -s			Silent (batch) mode (only for &quot;ex&quot;)
   -d			Diff mode (like &quot;vimdiff&quot;)
   -y			Easy mode (like &quot;evim&quot;, modeless)
   -R			Readonly mode (like &quot;view&quot;)
   -Z			Restricted mode (like &quot;rvim&quot;)
   -m			Modifications (writing files) not allowed
   -M			Modifications in text not allowed
   -b			Binary mode
   -l			Lisp mode
   -C			Compatible with Vi: &apos;compatible&apos;
   -N			Not fully Vi compatible: &apos;nocompatible&apos;
   -V[N][fname]		Be verbose [level N] [log messages to fname]
   -D			Debugging mode
   -n			No swap file, use memory only
   -r			List swap files and exit
   -r (with file name)	Recover crashed session
   -L			Same as -r
   -A			Start in Arabic mode
   -H			Start in Hebrew mode
   -F			Start in Farsi mode
   -T &lt;terminal&gt;	Set terminal type to &lt;terminal&gt;
   --not-a-term		Skip warning for input/output not being a terminal
   --ttyfail		Exit if input or output is not a terminal
   -u &lt;vimrc&gt;		Use &lt;vimrc&gt; instead of any .vimrc
   --noplugin		Don&apos;t load plugin scripts
   -p[N]		Open N tab pages (default: one for each file)
   -o[N]		Open N windows (default: one for each file)
   -O[N]		Like -o but split vertically
   +			Start at end of file
   +&lt;lnum&gt;		Start at line &lt;lnum&gt;
   --cmd &lt;command&gt;	Execute &lt;command&gt; before loading any vimrc file
   -c &lt;command&gt;		Execute &lt;command&gt; after loading the first file
   -S &lt;session&gt;		Source file &lt;session&gt; after loading the first file
   -s &lt;scriptin&gt;	Read Normal mode commands from file &lt;scriptin&gt;
   -w &lt;scriptout&gt;	Append all typed commands to file &lt;scriptout&gt;
   -W &lt;scriptout&gt;	Write all typed commands to file &lt;scriptout&gt;
   -x			Edit encrypted files
   --startuptime &lt;file&gt;	Write startup timing messages to &lt;file&gt;
   -i &lt;viminfo&gt;		Use &lt;viminfo&gt; instead of .viminfo
   --clean		&apos;nocompatible&apos;, Vim defaults, no plugins, no viminfo
   -h  or  --help	Print Help (this message) and exit
   --version		Print version information and exit
admin@sonic:~$ 
</pre>
---

$ history
---
<pre>admin@sonic:~$ history --help
history: history [-c] [-d offset] [n] or history -anrw [filename] or history -ps arg [arg...]
    Display or manipulate the history list.
    
    Display the history list with line numbers, prefixing each modified
    entry with a `*&apos;.  An argument of N lists only the last N entries.
    
    Options:
      -c	clear the history list by deleting all of the entries
      -d offset	delete the history entry at position OFFSET. Negative
    		offsets count back from the end of the history list
    
      -a	append history lines from this session to the history file
      -n	read all history lines not already read from the history file
    		and append them to the history list
      -r	read the history file and append the contents to the history
    		list
      -w	write the current history to the history file
    
      -p	perform history expansion on each ARG and display the result
    		without storing it in the history list
      -s	append the ARGs to the history list as a single entry
    
    If FILENAME is given, it is used as the history file.  Otherwise,
    if HISTFILE has a value, that is used, else ~/.bash_history.
    
    If the HISTTIMEFORMAT variable is set and not null, its value is used
    as a format string for strftime(3) to print the time stamp associated
    with each displayed history entry.  No time stamps are printed otherwise.
    
    Exit Status:
    Returns success unless an invalid option is given or an error occurs.
admin@sonic:~$ 
</pre>
---

$ date
---
<pre>admin@sonic:~$ date
Fri 15 Feb 2019 08:33:05 AM UTC
admin@sonic:~$ 
</pre>
---

$ pwd
---
<pre>admin@sonic:~$ pwd
/home/admin
admin@sonic:~$ 
</pre>
---

$ logout
---
<pre>admin@sonic:~$ logout

Debian GNU/Linux 10 sonic ttyS0

sonic login: 
</pre>
---

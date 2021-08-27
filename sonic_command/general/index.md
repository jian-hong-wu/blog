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
admin@sonic:~$ help
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
<pre>admin@sonic:~$ ls
junk
admin@sonic:~$ 
</pre>
---

$ dir
---
<pre>admin@sonic:~$ dir
junk
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

---

$ vi
---

---

$ history
---

---

$ date
---

---

$ export
---

---

$ pwd
---

---

$ logout
---

---

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

$ mkdir
---
<pre>admin@sonic:~$ mkdir directory
admin@sonic:~$ </pre>
---

$ cd
---
<pre>admin@sonic:~$ cd directory
admin@sonic:~/directory$ </pre>
---

$ rmdir
---
<pre>admin@sonic:~$ rmdir directory
admin@sonic:~$ 
</pre>
---

$ ls
---

---

$ dir
---

---

$ rm
---

---

$ cat
---

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

# Cycle filenames and autocomplete

>Tags: [[linux-kernel-for-embeded-systems]] [[bash]] [[productivity]] 

By default TAB auto-completion in linux adds the end of the path until there is no variations. But what if amount of variations is to big to type? That will make auto-completion less effective. However there is an option to cycle through filenames - it is called `menu-complete`.   

First it is necessary to add:   

```bash   
bind TAB:menu-complete
```   

to `~/.bashrc` or any other bash configuration file.   
Then, to make it work, it is necessary to reload the configurations.   

```bash
source ~/.bashrc
```

Now TAB key will cycle through filenames but will not complete it. To make it work at the same time we need to add folowing setting to `~/.inputrc`.   

```bash   
set show-all-if-ambiguous on
set show-all-if-unmodified on
set menu-complete-display-prefix on
"\t": menu-complete
"\e[Z": menu-complete-backward
```

Now TAB key will cycle through files and autocomplete when possible and Shift-TAB will cycle names backwards.

## Links
- read more about .inputrc settings in `man bash` at the sections `Readline Variables` and `Completing`.   
- [Stackexchange](https://unix.stackexchange.com/questions/24419/terminal-autocomplete-cycle-through-suggestions)

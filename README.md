# Bash it

Cloned from https://github.com/revans/bash-it

Install this for yourself by doing this:

```
cd 
git clone https://github.com/robparrott/bash_it/ .bash_it
```


Enable it by adding to your `.bash_profile`:

```
#----------------------------
# Setup BASH-IT
#
#    https://github.com/revans/bash-it
#
#----------------------------

_setup_bash_it () {

  # Load RVM, if you are using it
  [[ -s $HOME/.rvm/scripts/rvm ]] && source $HOME/.rvm/scripts/rvm

  # Add rvm gems and nginx to the path
  export PATH=$PATH:~/.gem/ruby/1.8/bin:/opt/nginx/sbin

  # Path to the bash it configuration
  export BASH_IT=$HOME/.bash_it

  # Lock and Load a custom theme file
  # location /.bash_it/themes/
  export BASH_IT_THEME='parrott'

  # Your place for hosting Git repos. I use this for private repos.
  export GIT_HOSTING='git@github.com'

  # Set my editor and git editor
  export EDITOR="/usr/local/bin/joe "
  export GIT_EDITOR='/usr/local/bin/joe '

## Misc

### Bash Profile Aliases
Bash it creates a 'reload' alias that makes it convenient to reload
your bash profile when you make changes.

### Prompt Version Control Check
Bash it provides prompt themes the ability to check and display version control information for the current directory. The information is retrieved for each directory and can slow down the navigation of projects with a large number of files and folders. Turn version control checking off to prevent slow directory navigation within large projects. 

Bash it provides a flag (`SCM_CHECK`) within the `~/.bash_profile` file that turns off/on version control information checking and display within all themes. Version control checking is on by default unless explicitly turned off. 

Set `SCM_CHECK` to 'false' to **turn off** version control checks for all themes: 

* `export SCM_CHECK=false`

Set `SCM_CHECK` to 'true' (the default value) to **turn on** version control checks for all themes: 

* `export SCM_CHECK=true`

**NOTE:**
It is possible for themes to ignore the `SCM_CHECK` flag and query specific version control information directly. For example, themes that use functions like `git_prompt_vars` skip the `SCM_CHECK` flag to retrieve and display git prompt information. If you turned version control checking off and you still see version control information  within your prompt, then functions like `git_prompt_vars` are most likely the reason why. 

## Help out

  # Set the path nginx
  #export NGINX_PATH='/opt/nginx'

  # Don't check mail when opening terminal.
  unset MAILCHECK

  # Change this to your console based IRC client of choice.
  export IRC_CLIENT='irssi'

  # Set this to the command you use for todo.txt-cli
  export TODO="t" #echo (None)"

  # Set vcprompt executable path for scm advance info in prompt (demula theme)
  # https://github.com/xvzf/vcprompt
  export VCPROMPT_EXECUTABLE=/usr/local/bin/vcprompt

  # Load Bash It
  source $BASH_IT/bash_it.sh

}
```

Then somewhere appropriate in your `.bash_profile` enable it with
```
_setup_bash_it
```

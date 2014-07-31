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

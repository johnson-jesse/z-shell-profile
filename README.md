# z-shell-profile
MacBook Pro .zshrc file

```zsh
export JAVA_HOME=$(/usr/libexec/java_home)
export PATH=/opt/apache-maven-3.6.3/bin:$PATH

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

# ------ Custom Prompt START
# https://scriptingosx.com/2019/07/moving-to-zsh-06-customizing-the-zsh-prompt/
# https://jonasjacek.github.io/colors/
# https://geoff.greer.fm/lscolors/

PROMPT='%(?.%F{green}✔︎.%F{red}✘[%?])%f %B%F{240}%1~%f%b %# '

autoload -Uz vcs_info
precmd_vcs_info() { vcs_info }
precmd_functions+=( precmd_vcs_info )
setopt prompt_subst
RPROMPT=\$vcs_info_msg_0_
zstyle ':vcs_info:git:*' formats '%F{240}(%b)%r%f'
zstyle ':vcs_info:*' enable git

export CLICOLOR=1
export LSCOLORS=cxfxexdxbxegedabagacad
# ------ Custom Prompt END
```

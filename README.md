# zshell
Plugins and Zshell Configuration

````
sudo apt update && sudo apt install zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k
wget https://github.com/powerline/powerline/raw/develop/font/PowerlineSymbols.otf
wget https://github.com/powerline/powerline/raw/develop/font/10-powerline-symbols.conf
mkdir ~/.local/share/fonts/
mv PowerlineSymbols.otf ~/.local/share/fonts/
fc-cache -vf ~/.local/share/fonts/
mkdir ~/.config/fontconfig/conf.d -p
mv 10-powerline-symbols.conf ~/.config/fontconfig/conf.d/
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
````

Edit ~/.zshrc configuration file
````
ZSH_THEME="powerlevel9k/powerlevel9k"
plugins=(zsh-autosuggestions)

````

## Alias
````
alias micon="pactl load-module module-loopback latency_msec=1"
alias micoff="pactl unload-module module-loopback"
alias ll="exa -l"
alias la="exa -la"
alias cat="batcat"
alias hg="history | grep "
alias rasp="ssh -i ~/.ssh/id_rsa_sismico pi@192.168.10.11"
alias raspnoelia="ssh -p 4022 -i ~/.ssh/id_rsa_sismico pi@noelia.sismico.ddnsfree.com"
alias raspintegrativapet="ssh -p 4022 -i ~/.ssh/id_rsa_sismico pi@integrativapet.sismico.ddnsfree.com"
````

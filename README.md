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
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
````

Edit ~/.zshrc configuration file
````
ZSH_THEME="powerlevel9k/powerlevel9k"
plugins=(zsh-autosuggestions zsh-syntax-highlighting)

````

## Alias
````
alias micon="pw-link alsa_input.pci-0000_04_00.6.analog-stereo.2:capture_FL alsa_output.usb-Kingston_HyperX_QuadCast_S_4100-00.analog-stereo:playback_FL && pw-link alsa_input.pci-0000_04_00.6.analog-stereo.2:capture_FR alsa_output.usb-Kingston_HyperX_QuadCast_S_4100-00.analog-stereo:playback_FR"
alias micoff="pw-link -d alsa_input.pci-0000_04_00.6.analog-stereo.2:capture_FL alsa_output.usb-Kingston_HyperX_QuadCast_S_4100-00.analog-stereo:playback_FL && pw-link -d alsa_input.pci-0000_04_00.6.analog-stereo.2:capture_FR alsa_output.usb-Kingston_HyperX_QuadCast_S_4100-00.analog-stereo:playback_FR"
alias ll="exa -l"
alias la="exa -la"
alias cat="batcat"
alias hg="history | grep "
alias rasp="ssh -i ~/.ssh/id_rsa_sismico pi@192.168.10.11"
alias raspnoelia="ssh -p 4022 -i ~/.ssh/id_rsa_sismico pi@noelia.sismico.ddnsfree.com"
alias raspintegrativapet="ssh -p 4022 -i ~/.ssh/id_rsa_sismico pi@integrativapet.sismico.ddnsfree.com"
alias brave-limit='systemd-run --scope -p MemoryLimit=4G --user brave'
alias database="az account get-access-token --resource https://ossrdbms-aad.database.windows.net/ | jq .accessToken -r"
alias monitor-left-right='xrandr --output "DP-1" --auto && sleep 2s && xrandr --output "DP-1" --auto && sleep 5s && xrandr --output "DP-1" --left-of "HDMI-1"'
alias monitor-right='xrandr --output "DP-1" --off'
````

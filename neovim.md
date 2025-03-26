## Install neovim
```shell
sudo apt install neovim
```

## Uninstall neovim
```bash 
sudo apt remove neovim -y
sudo apt autoremove -y
sudo apt clean
```

remove the following files
```shell
rm -rf ~/.config/nvim
rm -rf ~/.local/share/nvim
rm -rf ~/.local/state/nvim
rm -rf ~/.cache/nvim
```
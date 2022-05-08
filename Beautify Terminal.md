###### Tags: `Terminal`
# Beautify Terminal

Through this tutorial, you’ll be able to make your terminal looks super cool. If you can’t beat others with coding, at least beat them with good Terminal interface 👍.


Many people recommand installing iTerm, but I think the Terminal build into Mac is good enough, so there’s no need to install another terminal.

## Install Nerd Font

To make your Terminal look better, fonts are important. [Nerd Fonts](https://www.nerdfonts.com/#home) is a project that patches developer targeted fonts with a high number of icons.

![](https://i.imgur.com/duj090m.png)

There are several ways to install nerd fonts. I’m a mac user, so I use [Homebrew](https://brew.sh/index_zh-tw) to install it, which makes everything easier to handle. 

:::info
💡 Homebrew is a package manager, that makes install, update, uninstall applications and utilities on Mac easier with simple command lines.
:::


> You can checkout [this link](https://github.com/ryanoasis/nerd-fonts#font-installation) to find out other ways to install nerd fonts.
> 

```bash=zsh 
brew tap homebrew/cask-fonts
brew install --cask font-hack-nerd-font
```

After successfully installing nerd fonts. Remember to change fonts in your Terminal.

Preference → Profile → Text → Font → Change

![](https://i.imgur.com/KwvscIs.png)

---

## Install zsh

[zsh](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH) is an extended version of the bash.

Use homebrew to install it

```bash=zsh
brew install zsh
```

Set zsh as your default shell

```bash=zsh
chsh -s /usr/local/bin/zsh
```

---

## Install powerlevel10k

```bash=zsh
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k
echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >>~/.zshrc
```

---

### Setup powerlevel10k

After type in command lins above, restart zsh with <font color="red">`exec zsh`</font> ( or you can just reopen your Terminal), and it will appear a series of configuration. 

There are several commands you can use if you type in <font color="red">`p10k command`</font>

![](https://i.imgur.com/NnkEQax.png)

Finally, you will get a customised Terminal interface

![](https://i.imgur.com/fbtyvgH.png)

---
If you want to have cool icon show on your terminal, you can checkout [colorls](https://github.com/athityakumar/colorls) , you’re terminal will look like this 

## Colorls

![](https://i.imgur.com/enjw2PR.png)

---

# Reference

- [Nerd Font](https://www.nerdfonts.com/#home)
- [zsh](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH)
- [powerlevel10k](https://github.com/romkatv/powerlevel10k)
- [colorls](https://github.com/athityakumar/colorls#custom-configurations)
# 🚀 Ubuntu Terminal Setup Guide: Zsh Awesomeness

Transform your boring terminal into a powerful, beautiful, and highly productive workspace using Zsh, Oh My Zsh, and Powerlevel10k.

---

## 📋 Table of Contents
- [Prerequisites](#-prerequisites)
- [Step 1: Update System](#step-1-update-system)
- [Step 2: Install Zsh](#step-2-install-zsh)
- [Step 3: Install Git](#step-3-install-git)
- [Step 4: Install Oh My Zsh](#step-4-install-oh-my-zsh)
- [Step 5: Install Essential Plugins](#step-5-install-essential-plugins)
  - [Zsh Autosuggestions](#zsh-autosuggestions)
  - [Zsh Syntax Highlighting](#zsh-syntax-highlighting)
- [Step 6: Install Powerlevel10k Theme](#step-6-install-powerlevel10k-theme)
- [Step 7: Install Font Awesome](#step-7-install-font-awesome)
- [Step 8: Final Touches](#step-8-final-touches)

---

## 🛠 Prerequisites
Before starting, ensure you have a stable internet connection and sudo privileges.

### Step 1: Update System
Always start with a fresh system.
```bash
sudo apt-get update && sudo apt-get upgrade -y
```

---

## 🐚 The Shell: Zsh

### Step 2: Install Zsh
Install the Zsh shell itself.
```bash
sudo apt install zsh -y
```
> [!IMPORTANT]
> After installation, **close your terminal, log out, and log back in**. When you re-open the terminal, Zsh will ask for initial configuration. Press `0` to create a blank `.zshrc` file (we will configure it later).

---

## 🔧 Tools & Frameworks

### Step 3: Install Git
Git is required for downloading themes and plugins.
```bash
sudo apt install -y git
```

### Step 4: Install Oh My Zsh
Oh My Zsh is a delightful, open-source, community-driven framework for managing your Zsh configuration.
```bash
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

---

## 🔌 Enhancing Productivity: Plugins

### Step 5: Install Essential Plugins

#### Zsh Autosuggestions
It suggests commands based on your history as you type.
```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

#### Zsh Syntax Highlighting
It provides syntax highlighting for the Zsh shell. It helps in catching syntax errors before hitting enter.
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

#### ⚙️ Configure Plugins
Open your `.zshrc` file:
```bash
nano ~/.zshrc
```
Find the `plugins=(...)` line and replace it with:
```bash
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
```

---

## 🎨 Aesthetics: Themes & Fonts

### Step 6: Install Powerlevel10k Theme
Powerlevel10k is a theme for Zsh that emphasizes speed, flexibility, and out-of-the-box experience.
```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

#### ⚙️ Apply Theme
Open your `.zshrc` file again:
```bash
nano ~/.zshrc
```
Change the `ZSH_THEME` line to:
```bash
ZSH_THEME="powerlevel10k/powerlevel10k"
```

### Step 7: Install Font Awesome
For the icons to render correctly in Powerlevel10k.
```bash
sudo apt install -y fonts-font-awesome
```

---

## ✨ Step 8: Final Touches
Close and re-open your terminal. You will be greeted by the **Powerlevel10k Configuration Wizard**.

1. Answer the questions to customize your prompt (Icons, Rainbow, etc.).
2. If the wizard doesn't start automatically, run:
   ```bash
   p10k configure
   ```

**Enjoy your awesome new terminal! 🚀**

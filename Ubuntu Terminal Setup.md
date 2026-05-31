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
  - [Configure Plugins](#configure-plugins)
- [Step 6: Install Powerlevel10k Theme](#step-6-install-powerlevel10k-theme)
  - [Apply Theme](#apply-theme)
- [Step 7: Install Nerd Fonts and Awesome Fonts](#step-7-install-nerd-fonts-and-awesome-fonts)
  - [Install Meslo Nerd Font](#step-7a-install-meslo-nerd-font)
  - [Install Font Awesome UI Icons](#step-7b-install-font-awesome-ui-icons)
  - [Editor (VS Code, Antigravity) Preferences Setup](#step-7c-editor-vs-code-antigravity-preferences-setup)
- [Step 8: Final Touches](#-step-8-final-touches)

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

#### Configure Plugins
Open your `.zshrc` file:
```bash
nano ~/.zshrc
```
Find the `plugins=(...)` line and replace it with:
```bash
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
```
Remove Comment (#) from this line: 
```bash
export PATH=$HOME/bin:$HOME/.local/bin:/usr/local/bin:$PATH
```
---

## 🎨 Aesthetics Themes

### Step 6: Install Powerlevel10k Theme
Powerlevel10k is a theme for Zsh that emphasizes speed, flexibility, and out-of-the-box experience.
```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

#### Apply Theme
Open your `.zshrc` file again:
```bash
nano ~/.zshrc
```
Change the `ZSH_THEME` line to:
```bash
ZSH_THEME="powerlevel10k/powerlevel10k"
```
---

## 🔥 Fonts & UI Icons

### Step 7: Install Nerd Fonts and Awesome Fonts
- To enable icons and glyphs in your terminal (Zsh, Oh My Zsh, Powerlevel10k), install a Nerd Font.  
- Web/UI tools rely on Font Awesome icons  
- ✔ **Installing both ensures maximum compatibility** across tools

#### Step 7A: Install Meslo Nerd Font

```bash
# Create fonts directory (if not exists)
mkdir -p ~/.local/share/fonts

# Move into fonts directory
cd ~/.local/share/fonts

# Download Meslo Nerd Font
wget https://github.com/ryanoasis/nerd-fonts/releases/latest/download/Meslo.zip

# Extract the font package
unzip Meslo.zip

# Refresh font cache
fc-cache -fv
```


#### Step 7B: Install Font Awesome UI Icons
For the icons to render correctly in Powerlevel10k.
```bash
sudo apt install -y fonts-font-awesome
```

#### Step 7C: Editor (VS code, Antigravity) Preferences Setup 

- Open Preferences using `Ctrl + Shift + P`
- Search and select **Open User Settings (JSON)**
- Add this configuration:
```json
"terminal.integrated.fontFamily": "MesloLGS Nerd Font Mono"
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

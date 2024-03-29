# Environment Config (Use defaults for install):

#### 1. Install [Visual Studio Code](https://code.visualstudio.com/docs/?dv=win64user).

#### 2. Install [nvm-windows](https://github.com/coreybutler/nvm-windows) (Node Version Manager for Windows). Download the latest release of nvm-setup.exe
   
   + Open Command Prompt and run the commands below to configure nvm to use an LTS(Long Term Support) version of node
     ```
     nvm (to check if nvm is working correctly)
     nvm install lts
     ```
# Fish-on-Windows (Friendly Interactive SHell)

## Using fish shell on Windows

### Install
#### 1. Install [Cygwin](https://www.cygwin.com/setup-x86_64.exe) ( This will be our linux terminal emulator )
#### 2. Select defaults till it open a package setup screen. From here we'll install some useful packages. First click on View in the top left and select "All" then search for the following         packages and on the "New" column click the drop down and select the latest version.
   + curl
   + fish
   + git
   + nano
   + wget
     
   + <img width="672" alt="301260999-0822f49d-24db-4f85-8175-8e27b153cac7" src="https://github.com/cyb0rg56/Fish-on-Windows/assets/46009508/824b37bc-56a4-4643-aaf9-7f198844b16b">

   + <img width="672" alt="301261145-73ea3858-3a99-4c49-83ea-18a131e39c57" src="https://github.com/cyb0rg56/Fish-on-Windows/assets/46009508/4c648258-78d1-4877-8b28-5ea9bb8e8eeb">


#### 3. Finish off the install. This'll take 5-10 mins.
     
#### 4. Install [Starship](https://github.com/starship/starship/releases/) ( This is an awesome prompt for the fish shell )
   + Download the latest release of Starship with the name `starship-x86_64-pc-windows-msvc.msi`
   + Download fonts, extract them, select all, right click and install them all. [FiraCode Fonts](https://github.com/ryanoasis/nerd-fonts/releases/download/v3.1.1/FiraCode.zip)
   + <img width="996" alt="301260250-0087462b-60d6-481b-a810-e866461dec95" src="https://github.com/cyb0rg56/Fish-on-Windows/assets/46009508/c31ea0bd-3bd7-44ea-806d-a7875689bfe6">


#### 5. Set your newly installed fonts in Cygwin.
   + You can do this by opening up a cygwin terminal, then right clicking the top bar of the window and clicking "Options"
   + <img width="497" alt="301259762-7ba3df6b-3f5f-400c-af5e-eab0f691fa15" src="https://github.com/cyb0rg56/Fish-on-Windows/assets/46009508/37f0e049-db17-40f3-b32f-ace1425b0fa9">
   + Go to "Text" tab and then "Select", you can now search for `FiraCode Nerd Font Mono`
   + <img width="291" alt="301262433-7e509325-4178-4d39-b643-abe9c5ed2376" src="https://github.com/cyb0rg56/Fish-on-Windows/assets/46009508/cd53097d-6fbd-4d49-bf7e-ca8c7fb9544f">




## Cygwin Config

### SSH Keys
#### 1. To create an SSH Key, run the command below but replace with your GitHub email. Give the key a name.
```
ssh-keygen -t ed25519 -C "your_email@example.com"
```
+ Now we need to cat the ssh file we just created and copy the value.
```
cat ~/.ssh/NAME_OF_KEY.pub
```
+ Add the SSH key to Github SSH keys

### Fish Config
#### 2. Open up nano with the following path
```
nano ~/.config/config.fish
```

+ <img width="456" alt="301263415-3f1ff709-915a-40a4-ada7-d973a662899b" src="https://github.com/cyb0rg56/Fish-on-Windows/assets/46009508/756a172b-0542-45fe-9c7c-1d7e27a344b5">


#### 3. Add the following to the config.fish file at the bottom after "end". This will make starship the default prompt and will set your default path for fish to be C:\Users\{USER_NAME}\Projects
+ First create a Projects folder
```
starship init fish | source 
cd /cygdrive/c/Users/{ENTER_YOUR_USERNAME_HERE}/Projects
``` 
+ <img width="456" alt="301270129-65addead-515e-4276-ae82-4d610b89990c" src="https://github.com/cyb0rg56/Fish-on-Windows/assets/46009508/b93d3a6b-6e20-4802-bcfc-be483f940393">



## VS Code Config
#### 1. Configuring VS Code to use our newly configured terminals. 
   + Add the snippet below inside the curly braces of your VS Code settings.json file. This is located in `C:\Users\Humza Khan\AppData\Roaming\Code\User\`
```
"terminal.integrated.defaultProfile.windows": "Cygwin-Fish",
    "terminal.integrated.profiles.windows": {
        "Cygwin-Fish": {
            "path": "C:\\cygwin64\\bin\\fish.exe",
            "args": ["--login"],
            "env": {"CHERE_INVOKING": "1"}
        },
        "Cygwin-Bash": {
            "path": "C:\\cygwin64\\bin\\bash.exe",
            "args": ["--login"],
            "env": {"CHERE_INVOKING": "1"}
        }
    },
    "terminal.integrated.fontFamily": "\"FiraCode Nerd Font\", Monaco",
```
+ <img width="1280" alt="301263706-77102390-4c4b-4541-a2ac-12fba9a220f2" src="https://github.com/cyb0rg56/Fish-on-Windows/assets/46009508/76fa5fee-c6d8-4189-9d15-c88ad4e3b4ee">



### Tool sources

[CygWin Project](https://cygwin.com/)
[Starship Prompt](https://starship.rs/)
[NerdFonts](https://www.nerdfonts.com/font-downloads)
[Fish](https://fishshell.com/)

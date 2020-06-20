# Terminal Setup

Steps for getting a customizable terminal config.

1. First we will install a package manager for MacOS called [Homebrew](https://brew.sh/)
    - Open the terminal by clicking on the Launchpad Icon at the bottom and typing the word `terminal`:

      ![launchpad icon](select_terminal.png)
      
    - Copy and paste the following script into your Terminal and hit enter: 
      ```bash
      /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
      ```
      
1. Next we will replace our terminal with [iTerm2](https://iterm2.com/) a terminal emulator. Download the latest stable release. Unzip the download by opening the file with the Archive Utility
    
    ![opening iterm](open_iterm.png)
    - To be able to access the application from the Launchpad we need to drag the application into the application folder:
    ![opening iterm](move_application.gif)
    
1. Now we need to get someway of addding plugins to our terminal. We will install [Oh My Zsh](https://github.com/ohmyzsh/ohmyzsh#basic-installation), a  community-driven framework for managing your zsh configuration. Input the following scripts:
    1.  ```bash
        brew install zsh
        ```
    1.  ```bash
        sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
        ```

1. Next we will install something to assist us with our terminal commands. We will be Installing [Starship](https://starship.rs/guide/#with-homebrew).
    1.  ```bash
        brew install starship
        ```
        - follow any prompts. Then run:
    1.  ```bash
        echo 'eval "$(starship init zsh)"' >> ~/.zshrc
        ```
        - Restart the terminal to let the configuration take effect.

1. Install [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md#oh-my-zsh) to enable syntax highlighting in the terminal.
    ```bash
    brew install zsh-syntax-highlighting 
    ```

6. Now to enable the installation prompts and plugins edit the `.zshrc` config file

    - In the terminal open the `.zshrc` config file in a text editor (VIM this case):

      ```bash
      vim ~/.zshrc
      ```

    - Now find the line starting with `ZSH_THEME=` and comment the line out by adding a `#` at the start of the line.

      ```bash
      # example config
      # ZSH_THEME="robbyrussell"
      ```

    - Then enable the `zsh-syntax-highlighting` plugin. Find the `plugin` directive in the config file and add `zsh-syntax-highlighting` to the end of the list of plugins:

      ```bash
        # Note, the 'zsh-syntax-highlight' plugin
        # "NEEDS" to go at the end of the the list 
        plugins=(git brew npm zsh-syntax-highlighting)
        ```
      - See this [FAQ for why the zsh-syntax-highlight plugin needs to go last](https://github.com/zsh-users/zsh-syntax-highlighting#why-must-zsh-syntax-highlightingzsh-be-sourced-at-the-end-of-the-zshrc-file).

      - Save config file.

7. Install `Powerline` symbols/fonts for the `Starship` prompt.

    - Download the `PowerlineSymbols.otf` font pack from Github: https://github.com/powerline/powerline/blob/develop/font/PowerlineSymbols.otf

    - Double click / open the downloaded font pack. This will open a `Font Book` window.

      - Click on the `Install font` button to install the font onto your system.
      ![Install font](install_font.png)

    - Update the iTerm preferences to use the `Powerline` fonts.

      - Switch to an iTerm window and click on the `iTerm2` menu item in the top left corner of the screen. Then select `Preferences`. Or use the shortcut keys `command` + `,`

      - In the `Preferences` window, switch to the `Profiles` tab (in the top of the Preferences window).

      - Select a profile (if not using the `Default` profile).

      - Select the `Text` tab on the right section.

      - Find and check the option `Use a different font form non-ASCII text`. This should now display the `Non-ASCII Font` section under the checkbox.

      - In the `Non-ASCII Font` section, click the font selection box and select `PowerlineSymbols`.
      ![selecting the powerlinefont](font_selection.png)

8. Restart the terminal or import the new settings:

    - ```shell
      source ~/.zshrc
      ```

Now you should have a terminal that looks something like this:

![Terminal](./terminal.png)

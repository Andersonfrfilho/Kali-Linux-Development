# Linux-Zsh-GNU-Kali-config-development 
  - (GNU=kali config)(Linux=[terminal,zsh])

  <p align="center">
    <a href="#">
      <img src="./images/logo.png" alt="logo" style="border-radius:16px; height: 250px;width:750px; margin-right: 10px;">
    </a>
    <h3 align="center">Configuration development - NodeJs | ReactJs | React-Native </h3>
  </p>

<hr/>

2. Configure your system

   - Install [Google Chrome](https://google.com/)
     - ```sudo apt install git-all```

      <hr/>
   - Install [git](https://git-scm.com/)
     - ```sudo apt install git-all```

      <hr/>
       
   - [Zsh](https://www.zsh.org/) default terminal
     - ```chsh -s $(which zsh)```

      <hr/>
       
   - Install [Firacode](https://github.com/tonsky/FiraCode) font
     - install package --fix-broken
       - ```sudo apt --fix-broken install```
     - install package font 
       - ```sudo apt install fonts-firacode```
      <hr/>
       
   - Install [Oh my zsh](https://ohmyz.sh/)
     - ```sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"```

      <hr/>
       
   - Install [SpaceshipTheme](https://github.com/denysdovhan/spaceship-prompt)
     - clone reposiory in ~
       - ```git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt"```
     - linking repository
       - ```ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"```

      <hr/>
       
   - [Theme Gnome Terminal Dracula](https://draculatheme.com/gnome-terminal/)
     - You'll need the `dconf` command (if you run a recent Gnome version). In Ubuntu,this can be installed by running:
       - ```sudo apt-get install dconf-cli```
     - In other distros you'll need to dig around to find it, search your repositories for dconf related packages.
     - After installing dconf, you can clone this repository to your machine.
       - ```git clone https://github.com/dracula/gnome-terminal```
       - ```cd gnome-terminal```
     - Then you can run the installation script:
       - ```./install.sh```
     - Open terminal gnome-terminal
     - setting
     - preference custom fonts

      <hr/>
         
   - Instal visual code
     - download visual studio code
       - ```https://code.visualstudio.com/download```
     - open folder download archive
     - run command
       - ```sudo dpkg -i code...```

      <hr/>
       
   - Using Spaceship
     - run command in directory `~` <- this directory /home/your_user
       - ```code .zshrc```
     - Set ZSH_THEME="spaceship" in your .zshrc.
        - ```ZSH_THEME="spaceship"```

      <hr/>
       
   - Install [plugins Zsh](https://zdharma.org/zinit/wiki/INTRODUCTION/)
     - run comand
       - ```sh -c "$(curl -fsSL https://raw.githubusercontent.com/zdharma/zinit/master/doc/install.sh)"```
       - restart terminal
       - open zshrc add in file
     - open `.zshrc`, and add file run command
       - ```code .zshrc```
       - ```
          ### End of Zinit's installer chunk
          zinit light zdharma/fast-syntax-highlighting
          zinit light zsh-users/zsh-autosuggestions
          zinit light zsh-users/zsh-history-substring-search
          zinit light zsh-users/zsh-completions
          zinit light buonomo/yarn-completion

          pasteinit() {
            OLD_SELF_INSERT=${${(s.:.)widgets[self-insert]}[2,3]}
            zle -N self-insert url-quote-magic # I wonder if you'd need `.url-quote-magic`?
          }

          pastefinish() {
            zle -N self-insert $OLD_SELF_INSERT
          }
          zstyle :bracketed-paste-magic paste-init pasteinit
          zstyle :bracketed-paste-magic paste-finish pastefinish

          SPACESHIP_PROMPT_ORDER=(
          user          # Username section
          dir           # Current directory section
          host          # Hostname section
          git           # Git section (git_branch + git_status)
          hg            # Mercurial section (hg_branch  + hg_status)
          exec_time     # Execution time
          line_sep      # Line break
          vi_mode       # Vi-mode indicator
          jobs          # Background jobs indicator
          exit_code     # Exit code section
          char          # Prompt character
          )
          SPACESHIP_USER_SHOW=always
          SPACESHIP_PROMPT_ADD_NEWLINE=false
          SPACESHIP_CHAR_SYMBOL="❯"
          SPACESHIP_CHAR_SUFFIX=" "
          ```
      - restart terminal

      <hr/>

    - Install [Nvm](https://github.com/nvm-sh/nvm)
      - run command
        - ```curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash```
      - Add file profile enviroment variable nvm past in `.zshrc` or `.bashrc`
        - ```
             export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
             [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
          ```
      - Install node 
        - ```nvm install --lts```
      - use node
        - ```nvm use --lts```

      <hr/>

    - Install [Yarn](https://classic.yarnpkg.com/pt-BR/docs/install)
      - run comand to add package repository
        - ```curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -```
      - write file
        - ```echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list```
      - install yarn
        - ```sudo apt update && sudo apt install --no-install-recommends yarn```

      <hr/>

    - Install JDK8 -> java development kit
      - install package
        - ```sudo apt-get install openjdk-8-jdk```
      - install drives x86
        - ```sudo apt-get install gcc-multilib lib32z1 lib32stdc++6```

    - Install [Android Stuio](https://developer.android.com/studio)
      - download Android Studio.tar.gz
      - extract file in directori `~` where home/user
      - create a file in `~/Android/Sdk`
      - add profile file `.zshrc`
      - java default `/usr/lib/jvm/java-8-openjdk-amd64`
      - ```
           export JAVA_HOME=CAMINHO_ANOTADO_COM_SUA_VERSÃO
           export ANDROID_HOME=~/Android/Sdk
           export PATH=$PATH:$ANDROID_HOME/emulator
           export PATH=$PATH:$ANDROID_HOME/tools
           export PATH=$PATH:$ANDROID_HOME/tools/bin
           export PATH=$PATH:$ANDROID_HOME/platform-tools
           # emiter shorcut Android studio
           export PATH=$PATH:~/android-studio/bin
        ```
      - add in before alias coment ```alias sudo='sudo env PATH=$PATH $@'```
      - run terminal ```studio.sh```
      - add proxy
      - automatic proxy
      - not import config
      - send realtory
      - (welcome) next
      - (install type) custom
      - select JAVA_HOME
      - using visual code for open files ```sudo code . --user-data-dir='.'```
      - add variables envoriment in bash/.bashrc file
    - Configure visual code
      - `shift` + `ctrl` + `p` find JSON preferenes
      - ```json
        {
          //Defini o tema e icones
          "workbench.colorTheme": "Dracula",
          "workbench.iconTheme": "material-icon-theme",
          //Aumenta font terminal
          "terminal.integrated.fontSize":14,
          "workbench.editor.enablePreview": false,
          //Configura tamanho e familia da fonte
          "editor.tabSize":2,
          "editor.fontSize": 14,
          "editor.lineHeight": 24,
          "editor.fontFamily": "Fira Code",
          "editor.fontLigatures":true,
          "workbench.editor.enablePreview": false,
          "explorer.compactFolders": false,
          "editor.renderLineHighlight":"gutter",
          "workbench.editor.labelFormat":"short",
          "cSpell.language": "en,pt,pt_BR",
          "javascript.updateImportsOnFileMove.enabled":"never",

          "breadcrumbs.enabled":true,
          "editor.parameterHints.enabled":false,
          "typescript.updateImportsOnFileMove.enabled":"never",
          "explorer.confirmDragAndDrop":false,
          "explorer.confirmDelete":false,
          "editor.rulers":[80,120],
          "terminal.integrated.shell.linux": "/bin/zsh",
          "editor.codeActionsOnSave": {
            "source.fixAll.eslint": true
          },
          "emmet.syntaxProfiles": { "javascript": "jsx" },
          "emmet.includeLanguages": { "javascript": "javascriptreact" },
          "files.associations": {
            ".sequelizerc": "javascript",
            ".stylelintrc": "json",
            ".prettierrc": "json"
          },
          "material-icon-theme.folders.associations": {
            "infra": "app",
            "entities": "class",
            "schemas": "class",
            "typeorm": "database",
            "repositories": "mappings",
            "http": "container",
            "migrations": "tools",
            "modules": "components",
            "implementations": "core",
            "dtos": "typescript",
            "fakes": "mock",
            "websockets": "pipe",
            "protos": "pipe",
            "grpc": "pipe"
          },

          "material-icon-theme.files.associations": {
            "ormconfig.json": "database",
            "tsconfig.json": "tune",
            "*.proto": "3d"
          },
        }
        ```
     - extensions
     
       * [carbon-now-sh](https://marketplace.visualstudio.com/items?itemName=ericadamski.carbon-now-sh)
       
       * [Code autocomplete](https://marketplace.visualstudio.com/items?itemName=svipas.code-autocomplete)
       
       * [Color Highlighting](https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight)
       
       * [Color picker](https://marketplace.visualstudio.com/items?itemName=anseki.vscode-color)
       
       * [Code Runner](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner)
       
       * [Code spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)
         
         * [Brazilian Portuguese - Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker-portuguese-brazilian)
         
         * [Fullstack - Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=rbalet.code-spell-checker-fullstack)
       
       * [DotEnv](https://marketplace.visualstudio.com/items?itemName=mikestead.dotenv)
       
       * [EditorConfig](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)
       
       * [Eslint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
       
       * [Git history](https://marketplace.visualstudio.com/items?itemName=donjayamanne.githistory)
       
       * [Git Lens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
       
       * [Import Cost](https://marketplace.visualstudio.com/items?itemName=wix.vscode-import-cost)
       
       * [Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare)
       
         - install extensions live shared
         
         - ```wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs```
       
       * [MarkDown Preview Enhanced](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced)
       
       * [Material Icon theme](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme)
       
       * [Omni Theme](https://marketplace.visualstudio.com/items?itemName=rocketseat.theme-omni)
       
       * [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
       
       * [Preview](https://marketplace.visualstudio.com/items?itemName=searKing.preview-vscode)
       
       * [vscode-styled-components](https://marketplace.visualstudio.com/items?itemName=jpoissonnier.vscode-styled-components)
       
       * [docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)
              
       * [handlebars](https://marketplace.visualstudio.com/items?itemName=andrejunges.Handlebars)
         * [install](ext install andrejunges.Handlebars)
       
       * [handlebars - preview](https://marketplace.visualstudio.com/items?itemName=greenbyte.handlebars-preview)
         * [install](ext install andrejunges.Handlebars)
       
       * [Bracket Pair Colorizer](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer)
         * [install](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer)

<hr/> 

3. install docker,docker-compose, docker-machine
   * update packages linux
     - ```sudo apt-get update```
   * **(opcional) case remove oldest versions** 
     - ```sudo apt-get remove docker docker-engine docker.io```
   * install docker package
     - ```sudo apt install docker.io```
   * Start and Automate Docker, the Docker service needs to be setup to run at startup. To do so, type in each command followed by enter
     - ```sudo systemctl start docker```
     - ```sudo systemctl enable docker```
     - Create the docker group if it does not exist
     - ```sudo groupadd docker```
     - Add your user to the docker group.
     - ```sudo usermod -aG docker $USER```
     - Run the following command or Logout and login again and run (that doesn't work you may need to reboot your machine first)
     - ```newgrp docker```
     - Check if docker can be run without root
     - ```docker run hello-world```
   * Testing success
     - ```docker --version```
   * Referencies
     - ```https://www.digitalocean.com/community/questions/how-to-fix-docker-got-permission-denied-while-trying-to-connect-to-the-docker-daemon-socket```
  - Install insomnia
  - install spotify
   * **Optional**
   * Install docker-compose 
     - ```sudo apt install docker-compose```
   * Install docker-machine
     - ```
          base=https://github.com/docker/machine/releases/download/v0.16.0 &&         
          curl -L $base/docker-machine-$(uname -s)-$(uname -m) >/tmp/docker-machine &&
          sudo mv /tmp/docker-machine /usr/local/bin/docker-machine &&
          chmod +x /usr/local/bin/docker-machine
       ```
   * testing 
     - ```docker-machine version```
   * create machine default
     - install virtual-box
       - ```sudo apt-get install virtualbox```
     - isntall machine default -d second plan, 
       - ```docker-machine create -d virtualbox temp.sysadmin.local```
       - path
         - ```eval $(docker-machine env temp.sysadmin.local)```
         - ```docker-machine env temp.sysadmin.local ```
     - initial machine default
       - ```docker-machine start default```
   * Back Docker-LocalMachine return enviroment variable
     - este comando troca para o docker local
     - ```eval "$(docker-machine env -u)"```
<hr/>

4. install [Insomnia](https://updates.insomnia.rest/downloads/windows/latest?app=com.insomnia.app&ref=)
   - download package
     - ```https://updates.insomnia.rest/downloads/windows/latest?app=com.insomnia.app&ref=```
   - go in file download packages
     - ```dpkg -i insomnia_dpkg_name...```

<hr/> 

5. install [Spotify](https://www.spotify.com/br/download/linux/)
   - register package curl
     - ```curl -sS https://download.spotify.com/debian/pubkey.gpg | sudo apt-key add - ```
     - ```echo "deb http://repository.spotify.com stable non-free" | sudo tee /etc/apt/sources.list.d/spotify.list```
   - Install packages
     - ```sudo apt-get update && sudo apt-get install spotify-client```
     
6. install [pgAdmin](https://www.pgadmin.org/download/pgadmin-4-python/)
   - install using version python
   - https://pypi.org/project/pgadmin4/

7. install [GIMP]
   - install run
   
     - ```sudo apt-get update```
     
     - ```sudo apt-get upgrade```
     
     - ```sudo apt-get install software-properties-common```
     
     - ```sudo add-apt-repository ppa:otto-kesselgulasch/gimp```
     
     - ```sudo apt-get update```
     
     - ```sudo apt-get install gimp```
     
 - **Comands commons que salvam xD** 
   - git
     - access develop
       - ```git checkout branch_name```
     - run 
       - ```git pull```
     
     - back to branch
       - ```git checkout branch_name```
     - run git merge develop
       - ```git merge branch_name```
   - Node
     - kill process nodeJs
       * case netstat command not found
         - ```sudo apt-get install net-tools```
       - see a process in port
         * ```sudo netstat -lpn |grep :'3000'```
       - kill the id process without aspas
         * ```kill -9 id_process```
   
   - Problems with emulator in projects react-native, when install dependencia, or bundle not start
      - Register bundle
        - ```npx react-native bundle --platform android --dev false --entry-file index.js --bundle-output android/app/src/main/assets/index.android.bundle --assets-dest android/app/src/main/res/```
      - reset cache
        - ```cd android;./gradlew clean;cd ..;npx react-native run-android;npx react-native start --reset-cache;```
      - link assets
        - ```npx react-native link```
   - Force kill process
     - alt + f2
     - click in program 
   - Comands Docker
     - list all dockers with id
       - ```docker $(docker ps -aq)```
     - stop all dockers with id's
       - ```docker stop $(docker ps -aq)```
     - remove all dockers
       - ```docker rm $(docker ps -aq)``` 
   - pgAdmin4
     - Supported platforms:
     - Debian 9 (Stretch), 10 (Buster)
     - Ubuntu 16.04 (Xenial), 18.04 (Bionic), 19.10 (Eoan), 20.04 (Focal)
     - Kali 2020.2 (Focal)
  
     - Install the public key for the repository (if not done previously):
       - ```curl https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo apt-key add```
     - Create the repository configuration file:
       - ```sudo sh -c 'echo "deb https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/focal pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update'```

     - Install for both desktop and web modes:
       - ```sudo apt install pgadmin4```

     - Install for desktop mode only:
       - ```sudo apt install pgadmin4-desktop```

     - Install for web mode only: 
       - ```sudo apt install pgadmin4-web``` 

     - Configure the webserver, if you installed pgadmin4-web:
       - ```sudo /usr/pgadmin4/bin/setup-web.sh```
       
     - Electron
     
       * possiveis erros
       * 17502:0812/101639.918679:FATAL:setuid_sandbox_host.cc(158)] The SUID sandbox helper binary was found, but is not configured correctly. Rather than run without sandboxing I'm aborting now. You need to make sure that /home/miyazaki/Documents/gluco/glucogear-device-upload/node_modules/electron/dist/chrome-sandbox is owned by root and has mode 4755.
       * ```CONFIG_USER_NS=y``` enables the user namespaces feature, but they're still restricted to privileged users by default. This suggests ```sysctl kernel.unprivileged_userns_clone=1```

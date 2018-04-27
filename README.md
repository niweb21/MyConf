# Mes configs

## package

    sudo apt-get install apt-transport-https

## Oh-my-zsh

    sudo apt-get install zsh

    sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

    ln -sf ~/workspace/MyConf/zsh/.zshrc ~/.zshrc
    ln -s ~/workspace/MyConf/zsh/myagnoster.zsh-theme ~/.oh-my-zsh/themes/


    git clone https://github.com/powerline/fonts.git
    cd fonts
    ./install.sh

Dans les préférence de votre terminal changer la police pour Ubuntu Mono derivative Powerline


### Hack Smile :

Vu qu'on a un user réseau et non en local, le changement de shell ne fonctionne pas. Du coup dans le .bashrc lancer zsh

## Git

    sudo add-apt-repository ppa:git-core/ppa
    sudo apt-get update
    sudo apt-get install git

    ln -s ~/workspace/MyConf/git/.gitconfig ~/.gitconfig
    npm install -g diff-so-fancy

    ln -s ~/workspace/MyConf/git/.gitignore_global ~/.gitignore_global

## Gitg 0.2.7 (interactive staging)

depuis https://launchpad.net/ubuntu/+source/gitg/0.2.7-2 download gitg_0.2.7-2.dsc gitg_0.2.7.orig.tar.xz gitg_0.2.7.debian.tar.xz

    dpkg-source -x gitg_0.2.7-2.dsc
    cd gitg-0.2.7
    sudo dpkg-buildpackage -uc -us //nécessite d'installer toute les dépendances requises
    cd ..

    sudo dpkg -i gitg_0.2.7-2_amd64.deb

    //garde cette version de gitg
    sudo apt-mark hold gitg

## NodeJs

    wget https://nodejs.org/dist/v8.6.0/node-v8.6.0-linux-x64.tar.xz
    sudo mv node-v8.6.0-linux-x64 /usr/local/lib/node-v8.6.0-linux-x64
    cd /usr/local/bin
    ln -s /usr/local/lib/node-v8.6.0-linux-x64/bin/node
    ln -s /usr/local/lib/node-v8.6.0-linux-x64/bin/npm
    ln -s /usr/local/lib/node-v8.6.0-linux-x64/bin/npx


Npm global package not root : https://github.com/sindresorhus/guides/blob/master/npm-global-without-sudo.md

    mkdir "${HOME}/.npm-packages"
    echo "prefix=${HOME}/.npm-packages" >> ${HOME}/.npmrc

Dans le .bashrc / .zshrc :

    export NPM_PACKAGES="${HOME}/.npm-packages"
    export PATH="$NPM_PACKAGES/bin:$PATH"
    # Unset manpath so we can inherit from /etc/manpath via the `manpath` command
    unset MANPATH # delete if you already modified MANPATH elsewhere in your config
    export MANPATH="$NPM_PACKAGES/share/man:$(manpath)"


    npm install -g jshint

## Sublime Text

https://www.sublimetext.com/docs/3/linux_repositories.html :

    wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
    echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
    sudo apt-get update
    sudo apt-get install sublime-text

## PHP

    sudo add-apt-repository ppa:ondrej/php
    sudo apt-get update
    sudo apt-get install php

## Composer

    mkdir ~/bin
    php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
    php -r "if (hash_file('SHA384', 'composer-setup.php') === '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
    php composer-setup.php --install-dir=/home/nifor/bin --filename=composer
    php -r "unlink('composer-setup.php');"

## PHP CodeSniffer

    sudo apt-get install php-xml
    composer global require squizlabs/php_codesniffer:^3.1.0

## PHP Cs fixer

    composer global require friendsofphp/php-cs-fixer:^2.7.1

## Meld

    sudo apt-get install meld

## Wheel scroll speed

https://askubuntu.com/questions/285689/increase-mouse-wheel-scroll-speed/304653#304653

    sudo apt-get install imwheel
    ln -s ~/workspace/MyConf/ubuntu/.imwheelrc ~/.imwheelrc

Add in Statup applications:
https://askubuntu.com/questions/48321/how-do-i-start-applications-automatically-on-login/48327#48327

## Ressource monitor

    sudo apt-get install indicator-multiload


## TLDR

    npm install -g tldr

#FZF (fussy search for zsh history)

https://mike.place/2017/fzf-fd/

### linuxbrew

    sh -c "$(curl -fsSL https://raw.githubusercontent.com/Linuxbrew/install/master/install.sh)"


    PATH="/home/linuxbrew/.linuxbrew/bin:/home/linuxbrew/.linuxbrew/sbin:$PATH"

## fzf

    brew install fzf
    y y y

## fd

    brew install fd

## MailHog

    go get mailHog ???

    export MH_API_BIND_ADDR=127.0.0.1:8025
    export MH_UI_BIND_ADDR=127.0.0.1:8025
    export MH_SMTP_BIND_ADDR=127.0.0.1:1025






PATH="$HOME/bin:$HOME/.local/bin:$PATH"

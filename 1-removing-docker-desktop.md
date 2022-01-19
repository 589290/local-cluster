# Removing Docker Desktop:  

```
brew uninstall docker
```

The above command will uninstall these apps from your system if they are installed with `brew` :  
- docker-desktop
- docker-daemon
- docker-cli (docker command line app)
- kubernetes (and any clusters you have)
- kubectl

If you did not install Docker Desktop via `brew`, the uninstall is quite tedious (especially when you have an enterprise policy that forces you to enter your password for each and every sudo command -- if that is the case, skip below to encapsulate all of these individual commands in a single sudo command):

```
sudo rm -rf /Applications/Docker.app
sudo rm -f /usr/local/bin/docker
sudo rm -f /usr/local/bin/docker-machine
sudo rm -f /usr/local/bin/docker-compose
sudo rm -f /usr/local/bin/docker-credential-desktop
sudo rm -f /usr/local/bin/docker-credential-ecr-login
sudo rm -f /usr/local/bin/docker-credential-osxkeychain
sudo rm -rf ~/.docker
sudo rm -rf ~/Library/Containers/com.docker.docker
sudo rm -rf ~/Library/Application\ Support/Docker\ Desktop
sudo rm -rf ~/Library/Group\ Containers/group.com.docker
sudo rm -f ~/Library/HTTPStorages/com.docker.docker.binarycookies
sudo rm -f /Library/PrivilegedHelperTools/com.docker.vmnetd
sudo rm -f /Library/LaunchDaemons/com.docker.vmnetd.plist
sudo rm -rf ~/Library/Logs/Docker\ Desktop
sudo rm -rf /usr/local/lib/docker
sudo rm -f ~/Library/Preferences/com.docker.docker.plist
sudo rm -rf ~/Library/Saved\ Application\ State/com.electron.docker-frontend.savedState
sudo rm -f ~/Library/Preferences/com.electron.docker-frontend.plist
```

Running all the above commands inside a single sudo command:
```
sudo sh -c '
    rm -rf /Applications/Docker.app && \
    rm -f /usr/local/bin/docker && \
    rm -f /usr/local/bin/docker-machine && \
    rm -f /usr/local/bin/docker-compose && \
    rm -f /usr/local/bin/docker-credential-desktop && \
    rm -f /usr/local/bin/docker-credential-ecr-login && \
    rm -f /usr/local/bin/docker-credential-osxkeychain && \
    rm -rf ~/.docker && \
    rm -rf ~/Library/Containers/com.docker.docker && \
    rm -rf ~/Library/Application\ Support/Docker\ Desktop && \
    rm -rf ~/Library/Group\ Containers/group.com.docker && \
    rm -f ~/Library/HTTPStorages/com.docker.docker.binarycookies && \
    rm -f /Library/PrivilegedHelperTools/com.docker.vmnetd && \
    rm -f /Library/LaunchDaemons/com.docker.vmnetd.plist && \
    rm -rf ~/Library/Logs/Docker\ Desktop && \
    rm -rf /usr/local/lib/docker && \
    rm -f ~/Library/Preferences/com.docker.docker.plist && \
    rm -rf ~/Library/Saved\ Application\ State/com.electron.docker-frontend.savedState && \
    rm -f ~/Library/Preferences/com.electron.docker-frontend.plist
';
```
# install Node.js and npm using NVM
NVM (Node Version Manager) is a bash script used to manage multiple active Node.js versions. NVM allows us to install and uninstall any specific Node.js version which means we can have any number of Node.js versions we want to use or test.
To install Node.js and npm using NVM on your CentOS system, follow these steps:

## Install NVM (Node Version Manager)
To download the nvm install script run the following command:
```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
```

The script will clone the nvm repository from Github to ~/.nvm and add the script Path to your Bash or ZSH profile.
```
=> Close and reopen your terminal to start using nvm or run the following to use it now:

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```
As the output above shows, you should either close and reopen your terminal or run the commands to add the path to nvm script to your current session.

To verify that nvm was properly installed type:
```
nvm --version
```

```
0.33.11
```

# Install Node.js using NVM On CentOS 7

Now that the nvm tool is installed we can install the latest available version of Node.js, by typing:
```
nvm install node
```

```
Downloading and installing node v11.0.0...
Downloading https://nodejs.org/dist/v11.0.0/node-v11.0.0-linux-x64.tar.xz...
######################################################################## 100.0%
Computing checksum with sha256sum
Checksums matched!
Now using node v11.0.0 (npm v6.4.1)
Creating default alias: default -> node (-> v11.0.0)
```

Verify the Node.js version, by typing:
```
node --version
```
```
v10.1.0
```
## Install multiple Node.js versions using NVM
Let's install two more versions, the latest LTS version and version 8.12.0

```
nvm install --lts
nvm install 8.12.0
```

Once LTS version and 8.12.0 are installed to list all installed Node.js instances type:

```
nvm ls
```

```
->      v8.12.0                         # ACTIVE VERSION
       v10.13.0
        v11.0.0
default -> node (-> v11.0.0)           # DEFAULT VERSION
node -> stable (-> v11.0.0) (default)
stable -> 11.0 (-> v11.0.0) (default)
iojs -> N/A (default)
lts/* -> lts/dubnium (-> v10.13.0)
lts/argon -> v4.9.1 (-> N/A)
lts/boron -> v6.14.4 (-> N/A)
lts/carbon -> v8.12.0
lts/dubnium -> v10.13.0
```
The output tell us that the entry with an arrow on the left (-> v8.12.0), is the version used in the current shell session and the default version is set to v11.0.0. Default version is the version that will be active when opening new shells.
To change the currently active version you can use the following command:

```
nvm use 10.13.0
```
The output will look like something this:

```
Now using node v10.13.0 (npm v6.4.1)
```

To change the default Node.js version type:
```
nvm alias default 10.13.0
```

```
default -> 10.13.0 (-> v10.13.0)
```

## Install development tools
To be able to build native modules from npm we will need to install the development tools and libraries:

```
sudo yum install gcc-c++ make
```

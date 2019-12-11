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
v10.1.0

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

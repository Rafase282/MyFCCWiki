# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

## Install Node.js with NPM
Info from [here.](https://github.com/nodesource/distributions#debinstall)

Ubuntu 15.10, Node.js v5.x:

```
curl -sL https://deb.nodesource.com/setup_5.x | sudo -E bash -
sudo apt-get install -y nodejs
```

io.js v3.x:

```
curl -sL https://deb.nodesource.com/setup_iojs_3.x | sudo -E bash -
sudo apt-get install -y iojs
```

## Install MongoDB
Note that MongoDB only supports LTS versions of Ubuntu officially.
More detailed instructions [here.](https://docs.mongodb.org/manual/tutorial/install-mongodb-on-ubuntu/)

```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv EA312927
```

```
echo "deb http://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list
```

```
sudo apt-get update
sudo apt-get install -y mongodb-org
```

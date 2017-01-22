# docker-run-command (drc) v0.1.0

[![License](http://img.shields.io/:license-mit-blue.svg)](http://doge.mit-license.org)
[![Github Issues](http://githubbadges.herokuapp.com/solidbrackets/docker-run-command/issues.svg?style=flat-square)](https://github.com/solidbrackets/docker-run-command/issues)
[![Pending Pull-Requests](http://githubbadges.herokuapp.com/solidbrackets/docker-run-command/pulls.svg?style=flat-square)](https://github.com/solidbrackets/docker-run-command/pulls)

The goal of this project is to make your live way easier when you want to use Docker to execute each cli command in a container instead of installing all packages (and versions) on your machine.

So if your are tired of passing way too many arguments to a docker run each time, you should take a look at the source code.

By default the script: 

* mounts the current folder into an /app folder in the container and sets the workdir
* mounts your ssh key / agent / socket / know_hosts so you can keep using your favorite package managers, connect to your servers or clone git projects
* sets the permission for files generated in the container to 777 since most containers run as root

## Usage

```
drc image command params

drc php:5.6-cli "php -S 0.0.0.0:8000 -t public/"

drc node:argon "npm test"
drc node:argon "node_modules/.bin/nodemon" "-p 4000:4000"
```

## Installing

You can copy/paste the file wherever you want or you can store it next to your other binaries.

```
sudo wget https://raw.githubusercontent.com/solidbrackets/docker-run-command/master/docker-run-command -O /usr/bin/drc
sudo chmod +x /usr/bin/drc
```

End with an example of getting some data out of the system or using it for a little demo

## Security

Since your ssh key is mounted you should only run containers you trust and in a controlled environment because all files generated in the /app folder will have 777 permissions on your host.

## Contributing

Feel free to create an issue. Pull requests are much appreciated.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/solidbrackets/docker-run-command/tags). 

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details


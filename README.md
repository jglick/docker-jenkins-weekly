# docker-jenkins-weekly

a docker image containing the latest jenkins weekly release and plugins, published here: https://hub.docker.com/r/jenkinsciinfra/jenkins-weekly

## Updating Plugins

```
bash ./bin/update-plugins.sh
```

This script uses the [Jenkins Plugin Manager Tool command line](https://github.com/jenkinsci/plugin-installation-manager-tool) under the hood to update the plugins.

## Update Jenkins Version

```
VERSION=$(jv get --version-identifier latest)
SUFFIX=jdk11
FULL_VERSION=jenkins/jenkins:${VERSION}-${SUFFIX}
sed -i 's|FROM .*|FROM '"${FULL_VERSION}"'|' Dockerfile
```

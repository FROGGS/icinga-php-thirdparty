Icinga Web 2 - ReactPHP-based 3rd party libraries
=================================================

This repository is an attempt to ship 3rd party libraries that might be useful
for asynchronous PHP-based Icinga Web 2 modules. Please download the latest
release and install it like any other module.

> **HINT**: Do NOT install the GIT master, it will not work! Checking out a
> branch like `stable/0.5.0` or a tag like `v0.5.0` is fine.

Sample Tarball installation
---------------------------

```sh
MODULE_NAME=reactbundle
MODULE_VERSION=v0.5.0
MODULES_PATH="/usr/share/icingaweb2/modules"
MODULE_PATH="${MODULES_PATH}/${MODULE_PATH}"
RELEASES="https://github.com/Icinga/icingaweb2-module-${MODULE_NAME}/archive"
mkdir "$MODULE_PATH" \
&& wget -q $RELEASES/${MODULE_VERSION}.tar.gz -O - \
   | tar xfz - -C "$MODULE_PATH" --strip-components 1
icingacli module enable "${MODULE_NAME}"
```

Sample GIT installation
-----------------------

```sh
MODULE_NAME=reactbundle
MODULE_VERSION=v0.5.0
REPO="https://github.com/Icinga/icingaweb2-module-${MODULE_NAME}"
MODULES_PATH="/usr/share/icingaweb2/modules"
git clone ${REPO} "${MODULES_PATH}/${MODULE_NAME}" --branch "${MODULE_VERSION}"
icingacli module enable "${MODULE_NAME}"
```

Developer Documentation
-----------------------

### Add a new dependency

    composer require author/library:version

### Create a new release

    ./bin/make-release.sh <version>

e.g.

    ./bin/make-release.sh 0.5.0

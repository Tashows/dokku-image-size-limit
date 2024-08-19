# dokku-image-size-limit

dokku-image-size-limit is a plugin for [dokku][dokku] that limits the size of images that can be deployed. It is useful for preventing large images from being deployed to your server.

## Installation

```shell
sudo dokku plugin:install https://github.com/Tashows/dokku-image-size-limit.git
```

### Upgrading from previous versions

```shell
sudo dokku plugin:update image-size-limit
```

## Commands

```
$ dokku image-size-limit:help
    image-size-limit:report (<app>|--global)        Check the current image size limit for an app or globally.
    image-size-limit:set (<app>|--global) bytes     Set the maximum allowed image size in bytes. Deployments that exceed this limit will be rejected.
    image-size-limit:help                           Show help for the image-size-limit plugin
```

## Usage
No limit is set by default. When the plugin is enabled, it will just output the image size of an app during deployment.

Set a limit for an app to 2GB:
```shell
dokku image-size-limit:set app_nane 2147483648
``` 

Set a global limit to 2GB:
```shell
dokku image-size-limit:set --global 2147483648
```

Unset the limit for an app:
```shell
dokku image-size-limit:set app_name
```

Unset the global limit:
```shell
dokku image-size-limit:set --global
```

Show the current limit for an app:
```shell
dokku image-size-limit:report app_name
```

Get a list of all apps and their image size limits:
```shell
dokku image-size-limit:report
```

[dokku]: https://github.com/dokku/dokku

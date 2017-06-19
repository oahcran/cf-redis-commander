# Welcome to cf-redis-commander!

## Overview

Wrapper of _redis-commander_ for cloud foundry.
Thanks to https://github.com/joeferner/redis-commander/.

This tool deployed at Cloud Foundry would be helpful for application team to validate the app bounded Redis service functionality through a Web Browser, if don't have direct connection to Redis service server.

the _cf-redis-commander_ is tested with nodejs buildpack _v1.5.36_

> cfenv - 1.0.4

> redis-commander - 0.3.2

## Deployment to Cloud Foundry

1) git clone this repository:

```
git clone https://github.com/oahcran/cf-redis-commander
cd cf-redis-commander
```

Remember to install [cf cli](https://github.com/cloudfoundry/cli/releases) and then get an account from your Cloud Foundry team or public Cloud Foundry offering [Pivotal Web Services](http://run.pivotal.io/).

2) Update the redis service at `manifest.yml`

```yaml
---
applications:
- name: cf-redis-commander
  memory: 256M
  instances: 1
  host: cf-redis-commander
  services:
    - <redis service instance>
```

3) Push the application and access from its URL:

```sh
cf push
```


**NOTE**

The deployment of _cf-redis-commander_ requires internet access to download _redis-commander _and its dependencies during staing phase. 

If using it at a Cloud Foundry environment without direct internet accesds, please ask the administrator to set **HTTP(s) Proxy** at [staging environment variable group](https://docs.cloudfoundry.org/devguide/deploy-apps/environment-variable.html#evgroups)


## About Redis Commander 

1. [Redis GUI](https://redislabs.com/blog/so-youre-looking-for-the-redis-gui/)

2. [Redis Commander](https://www.npmjs.com/package/redis-commander)

3. [cfenv](https://www.npmjs.com/package/cfenv)

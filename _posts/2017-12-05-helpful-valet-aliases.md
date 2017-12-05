---
layout:     post
title:      Helpful Laravel Valet aliases
date:       2017-12-05
summary:    Valet up, up, down, down, left, right, left, right, B, A.
---

Quick post. Just wanted to share some of my custom aliases to aid development using Laravel Valet as your dev server. It assumes a convention of using the `mysql` service for your databases, and a `docker-compose-valet.yml` file in the root of your project for project dependencies outside the remit of Valet. Aliases can of course be modified for your needs.

Simply add the following to your `.bash_profile`, `.zshrc` or other shell config of choice:

```bash
# Valet Up
vup() {
    # Start Valet
    valet start
    # Start MySql
    brew services start mysql
    # If a valet Dockerfile is present, run as daemon
    if [ -f docker-compose-valet.yml ]; then
        echo "👍    \e[4m\e[42m\e[30mValet Dockerfile found, running as daemon...\e[0m"
        docker-compose --file docker-compose-valet.yml up -d
    fi
}

# Valet Down
vdown() {
    # Stop Valet
    valet stop
    # Stop MySql
    brew services stop mysql
    # If a valet dockerfile exists then stop it
    if [ -f docker-compose-valet.yml ]; then
        echo "👍    \e[4m\e[42m\e[30mValet Dockerfile found, stopping...\e[0m"
        docker-compose --file docker-compose-valet.yml stop
    fi
}
```

If you have any ideas of how to improve the aliases, please do create a PR on the [Github repository](https://github.com/samturrell/valet-aliases). Please share and star ⭐️ on Github if you found it useful!

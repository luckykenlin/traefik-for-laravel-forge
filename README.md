# Traefik Proxy for Laravel Forge

[![Laravel Forge Site Deployment Status](https://img.shields.io/endpoint?url=https%3A%2F%2Fforge.laravel.com%2Fsite-badges%2Fed322e5f-fb4d-4ab8-9fab-d0d54ce4f4e3%3Fdate%3D1%26commit%3D1&style=plastic)](https://forge.laravel.com/servers/699880/sites/2038639)

[Traefik Proxy](https://doc.traefik.io/traefik/) will help you get routing configured on your server between multiple services.

This repo is a fork of [ijpatricio/traefik-for-forge](https://github.com/ijpatricio/traefik-for-forge), so be sure to check that out. There is an original blog post that accompanied that repo, https://blog.jpat.dev/how-to-deploy-docker-applications-with-laravel-forge, that gives a great overview of how to set up Traefik on Laravel Forge. That post was very helpful in getting Traefik working on Laravel Forge.

## Additional notes

The original README from the Traefik repository is below. The command sets up the basic auth used to protect your Traefik dashboard.

### Original instructions from forked repo

Step 1. Deploy Script
Refer to (deploy script)[./Taskfile], in function `baseDeployScript`

Step 2. Configure ENV variables, and set Traefik Dashboard password
!!! Recommended doing via SSH, even you could fdo it from Forge's UI "Run command"
```bash
chmod +x ./Taskfile

./Taskfile copyEnv

./Taskfile auth username password
```

Step 3. Permission
```bash
# Access the container
docker exec -it traefik /bin/sh

# Navigate to the directory and change permissions
chmod 600 acme.json

# Exit the container
exit

```

## License

The source code for the site is licensed under the MIT license, which you can find in
the MIT-LICENSE.txt file.

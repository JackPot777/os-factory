# Contributing Guidelines

The OSFactory project accepts contributions via GitHub pull requests. This document outlines the process to help get your contribution accepted.

## How to add a provider

Create the following :
```bash
export provider=yourprovider
echo 'creating the main playbook for provider'
touch ./plays/${provider}.build.playbook.yml
echo 'creating the jninja2 template for packer files'
touch ./plays/template/${provider}.packer.json.j2
echo 'creating the provider main folder'
mkdir -p ./plays/inc/${provider}
echo 'creating the file for images sharing'
touch ./plays/inc/${provider}/_${provider}_sharing.yml
echo 'creating the init (to get all the variables from provider)'
touch ./plays/inc/${provider}/_init.yml
echo 'creating the builder file (to build packer template'
touch ./plays/inc/${provider}/_packer_build.yml
echo 'creating the file for id grabbing'
touch ./plays/inc/${provider}/_packer_get_id.yml
echo 'creating the file for dependencies installation on the VM builder'
touch ./resource/dependencies/${provider}.install.yml
```

And start to code !
# OS Factory  [![Build Status](https://travis-ci.org/societe-generale/os-factory.svg?branch=master)](https://travis-ci.org/societe-generale/os-factory)
OSFactory is an image creation framework (OS) based on Packer and Ansible and is currently used within the Société Générale for the creation of all the images used on the Public Cloud.


* auto-gen TOC:
{:toc}

## How to install it

### AWS
Please run this command to install all dependencies.

``` ansible-playbook resource/dependencies/aws.install.yml -i "MY_IP," ```

#### Dependencies
#### For infrastructure
![Infrastructure](resource/img/infrastructure.png)

To create images on AWS, the EC2 instance must be created in the same location (same subnet and region) as the one where packer will start creating your image.


### Azure

#### How to install it

Please run this command to install all dependencies.

``` ansible-playbook resource/dependencies/azure.install.yml -i "MY_IP," ```

#### Dependencies
You need at least two subscription, and they need to be controlled by the SPN.
#### For infrastructure

1. Create a Ubuntu VM and set the Managed Service Identity according :
    https://docs.microsoft.com/en-us/azure/active-directory/managed-service-identity/overview
1. Create a SPN :
    https://docs.microsoft.com/en-us/cli/azure/create-an-azure-service-principal-azure-cli?toc=%2fazure%2fazure-resource-manager%2ftoc.json
1. On the Ubuntu VM create 2 environnement variables :
    ```bash
    export arm_client_id='yourclientid'
    export arm_client_secret='yoursecret'
    ```
### For project
- [ansible](https://www.ansible.com/)>= 2.4
- [awscli](https://aws.amazon.com/en/cli/)
- [boto3](https://github.com/boto/boto3)
- [boto](https://github.com/boto/boto)
- [packer](https://www.packer.io/)
- [Azure Cli 2.0](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest)

## License

[Apache 2.0](LICENSE)

## Author Information

This project has been created in 2017 by [Maxence Maireaux](https://github.com/Flemzord/) and Product Owner by [Yannick Neff](https://github.com/yannickneff).

## Contributor
- [Aurélien Maury (WeScale)](https://github.com/aurelienmaury)
- [Etienne Deneuve (Cellenza)](https://github.com/EtienneDeneuve)
- [Xavier Bloumine (Aneo)](https://github.com/BloumineX)

## Sponsorship
[![](resource/img/logo_societe_generale.png)](https://www.societegenerale.fr/)&nbsp;&nbsp;&nbsp;
[![](resource/img/logo_microsoft.png)](https://www.microsoft.com/)&nbsp;&nbsp;&nbsp;
[![](resource/img/logo_wescale.png)](http://www.wescale.fr/)&nbsp;&nbsp;&nbsp;
[![](resource/img/logo_cellenza.png)](http://www.cellenza.com/)

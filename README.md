# fnsi-configuration

Configuration and deployment scripts for the Ruby on Rails and Flask applications running on AWS.

## Prerequisites

*  You will need ansible >=2.3.0 installed locally.
*  You will need to have the AWS ssh private key stored somewhere locally (such as ~/.ssh/fnsi-aws-keys.pem) in order to connect to the instance. The ip is located in prod_inventory.
*  You will need to have the vault_password.txt file stored somewhere locally in order to decrypt the .env

## Provisioning and/or deployment

In order to provision a fresh AWS instance and deploy

      ansible-playbook -i provisioning/prod_inventory provisioning/prod-aws.yml --vault-password-file vault_password.txt

Subsequent deployments are done with the same
command. Based on https://github.com/rdsubhas/ruby-deploy-kickstart.

### Auth

Signup is via Google OAuth https://console.developers.google.com/apis/credentials?project=factuly-platform

If provisioning a new server or domain name, you'll have to authorize ownership of https://factu.ly through their console.

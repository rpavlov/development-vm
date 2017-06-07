# fnsi-configuration

Configuration and deployment scripts for the Ruby on Rails and Flask applications.

## Configuration

Based on https://github.com/rdsubhas/ruby-deploy-kickstart.

- Requires an SSH private key (fnsi-aws-keys.pem) in order to connect to the instance.
- Requires a vault_password.txt file to decrypt the .env file during provisioning/deployment. Not version controlled.

### deployment

AWS Production: ```ansible-playbook -i provisioning/prod_inventory provisioning/prod-aws.yml --vault-password-file .vault_password.txt```

Development vagrant: ```vagrant up prod``` and then ```vagrant provision prod``` for subsequent re-deploys.

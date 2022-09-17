# make connections

1. Create ssh key for Control Node
2. copy the public key paste in every manage node under:
   ~/.ssh/authorized_keys
3. remove other permisions of .ssh directory :
   ```bash
   chmod -R go= ~/.ssh
   ```
4. create ownership for required user ( in our case its ubuntu )
   ```bash
   chown -R ubuntu:ubuntu ~/.ssh
   ```

5. Now we add present ssh key to ssh-agent:
    ```bash
    ssh-agent bash
    ssh-add ~/.ssh/id_rsa
    ```
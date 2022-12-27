# ubuntu-setup
initial setup for Ubuntu server

## Setup SSH Id on remote server

`ssh-copy-id -i ~/.ssh/id_rsa.pub remote_username@server_ip_address`

## Disable password SSH

`sudo nano /etc/ssh/sshd_config`

### Manual replace

`sudo nano /etc/ssh/sshd_config`

```bash /etc/ssh/sshd_config
PasswordAuthentication no
ChallengeResponseAuthentication no
UsePAM no
```

### Script

```bash
sudo sed -i 's/PasswordAuthentication yes/PasswordAuthentication no/g' /etc/ssh/sshd_config && \
sudo sed -i 's/UsePAM yes/UsePAM no/g' /etc/ssh/sshd_config
```

### Restart SSH

`sudo systemctl restart ssh`

## Change SSH port

[todo]()

## References

- [How to Set Up SSH Keys on Ubuntu 20.04](https://linuxize.com/post/how-to-set-up-ssh-keys-on-ubuntu-20-04/)
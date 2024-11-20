# Using a Shared User
Since this is a shared user there are a few custom functions for committing changes via git from the Deep Racer:

`deepracer-ssh-keygen`: You first time logging on to this machine, run this command. You will be prompted for your ID, name, email, and passphrase. this will generate an ssh key for you to be able to push&pull from github. Make sure to copy the contents of `~/.ssh/id_rsa_<ID>.pub` to your github account.
 
`deepracer-ssh-add`: Run this each time you open a new session in user to make sure that your github profile is being set and used. This will prompt you for the ID and passphrase you set above. You will not be able to commit changes without doing this! If you try to commit changes without doing this git will prompt you to set the global user name & email. PLEASE DO NOT DO THIS.
 
`deepracer-encrypt-key`: Since this is a shared user, other people will have access to your private key. You can use this command to encrypt your private key with `gpg`. You will be prompted for your ID, and then be asked to set a passphrase. This will remove your `id_rsa_<ID>` private key, and create a `id_rsa_<ID>.gpg` encrypted file. The next time you run `deep-racer-ssh-add`, you will be prompted for this passphrase and the private key will be decrypted, and the encrypted file will be removed. Note that you have to run this command each time you log out, otherwise your private key will remain on the system unencrypted.
 
# How to connect to the robot
The robot is located in the IRL. it should be on pretty much all the time. To connect to the robot over ssh, you must be connected to the `IRLab_5` network. The IP address for the robot is `192.168.50.30`. The username is `deepracer`. Password for the robot `advRobotics#1234`.

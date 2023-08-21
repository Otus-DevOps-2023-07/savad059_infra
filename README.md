# savad059_infra
savad059 Infra repository

HW#3
1. One-line command to connect:
	- add to /etc/hosts

<code>51.250.85.111 bastion</code>

<code>10.128.0.15   someinternalhost</code>


 - command:

<code>ssh someinternalhost -J bastion</code>

1.* No keys command to connect:

- make file
 <code>~/.ssh/config</code>
- add to
 <code>~/.ssh/config</code>

<code>

        Host someinternalhost
                ForwardAgent yes
                StrictHostKeyChecking no
                AddKeysToAgent yes
                IdentityFIle ~/.ssh/id_rsa
                User savchenko_ev
                PubkeyAcceptedKeyTypes +ssh-rsa
                HostKeyAlgorithms +ssh-rsa
                ProxyJump bastion
                </code>

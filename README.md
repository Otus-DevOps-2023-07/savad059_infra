# savad059_infra
savad059 Infra repository

HW#3
1. One-line command to connect:
	- add to /etc/hosts
	  <code>
	   51.250.85.111 bastion
	   10.128.0.15   someinternalhost
	  </code>
	- command:
	ssh someinternalhost -J bastion

1.* No keys command to connect:
	- make file ~/.ssh/config
	- add to ~/.ssh/config
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

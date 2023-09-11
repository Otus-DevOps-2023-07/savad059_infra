# savad059_infra

Домашнее задание №3:

Подключение к someinternalhost. Вариант:

1. Прописать в /etc/hosts

51.250.11.16 bastion
10.128.0.22  someinternalhost

Команда:

ssh -o ProxyCommand="ssh -W %h:%p -i ~/.ssh/appuser appuser@bastion" -i ~/.ssh/appuser appuser@someinternalhost hostname -f

2. Добавить описание хоста в локальном конфиге ssh (~/.ssh/config)

Host someinternalhost
	        User appuser
	        IdentityFile ~/.ssh/appuser
	        ProxyCommand=ssh -W %h:%p -i ~/.ssh/appuser appuser@51.250.11.16

Команда

ssh someinternalhost


Впн-сервер на bastion

bastion_IP = 51.250.11.16
someinternalhost_IP = 10.128.0.22

# ansible_test
Файл ./inventory/hosts.txt - список хостов
Файлы ./inventory/group_vars содержат переменные с именами пользователей и путём к ключу. Так же тут пароль для mysql/phpMyAdmin
Запуск всей установки, с параметрами по-умолчанию - "ansible-playbook -i inventory/hosts.txt playbooks/provision.yml"
Так же можно отдельными плейбуками:
"mysql"
"nginx"
"php"
"redis"
"composer"
"phpadmin"
"redisadmin"
По-умолчанию, для каждого дистрибутива своя версия PHP, но можно установить необходимую: ansible-playbook -i inventory/hosts.txt -e "php_default_version_debian=7.2"   , например
Установка доп модулей для PHP сделана несколькими способами: в ./inventory/group_vars в PHP_mods_enable установит значение "yes", тогда поставятся прописанные мною или вписать вручную через ansible-playbook>
По тегам: делал примитивно,  - install-redis -- общая задача, - install-redis-rh -- только часть, которая отличается от - install-redis-deb

PS: Времени заняло больше чем ожидал, возможно что-то пропустил, не было возможности отдебажить на разных версиях CentOS/Debian
    Так же буду рад, если оставите свой фидбек, укажите на ошибки(ну, кроме паролей в group_vars)) )


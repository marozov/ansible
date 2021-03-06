**Домашнее задание**
Первые шаги с Ansible

**Описание:**
Подготовить стенд на Vagrant как минимум с одним сервером. На этом сервере используя Ansible необходимо развернуть nginx со следующими условиями:

- необходимо использовать модуль **yum/apt**;
- конфигурационные файлы должны быть взяты из шаблона **jinja2** с перемененными;
- после установки **nginx** должен быть в режиме **enabled в systemd**;
- должен быть использован notify для старта nginx после установки;
- сайт должен слушать на нестандартном порту - **8080**, для этого использовать переменные в **Ansible**.

С помощью команды **ansible-galaxy init roles/nginx** создаем роль. Эта команда создаст нам структуру папок и файлов для работы.

Запуск производиться следующим образом **ansible-playbook playbook/web.yml**. После запуска этого файла, вызывается файл **/roles/nginx/tasks/main.yml**.

Файл **ansible.cfg** должен лежать с **vagrantfile** в одной директории.

Также можно удалять установленную программу **nginx ansible -m yum -a "name=nginx state=absent" -b**.

Для запуска выполнить **vagrant up**

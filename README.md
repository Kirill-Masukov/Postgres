С помощью данного репозитория можно осуществить установку PostgreSql. Установка осуществляется по средствам раскатывания Ansible role.
 
Перед запуском роли необходимо скорректировать файл Ansible/roles/PostgreSql/tasks/main.yml, раздел env (POSTGRES_USER, POSTGRES_PASSWORD, POSTGRES_DB), указав свои значения. Так же в файле Ansible/inventory/hosts.yml, в разделе ansible_host – указать IP хоста. 

Запуск playbook осуществляется командой: ansible-playbook -i inventory/ postgresql.yml

Проверить работоспособность установки можно командой: docker run -it --rm postgres psql -h указать IP хоста -U указать user указать название BD (пример: docker run -it --rm postgres psql -h 158.160.55.176 -U user my_db)


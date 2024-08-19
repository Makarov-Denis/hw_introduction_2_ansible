# Домашнее задание к занятию 1 «Введение в Ansible» «Макаров Денис»

## Подготовка к выполнению

1. Установите Ansible версии 2.10 или выше.
2. Создайте свой публичный репозиторий на GitHub с произвольным именем.
3. Скачайте [Playbook](./playbook/) из репозитория с домашним заданием и перенесите его в свой репозиторий.

## Основная часть

1. Попробуйте запустить playbook на окружении из `test.yml`, зафиксируйте значение, которое имеет факт `some_fact` для указанного хоста при выполнении playbook.

Выполнение задания представлено на скриншоте ниже:

![some_fact](https://github.com/user-attachments/assets/8ab6f140-fbbd-4498-8c9b-7806e810e242)

2. Найдите файл с переменными (group_vars), в котором задаётся найденное в первом пункте значение, и поменяйте его на `all default fact`.

Выполнение задания представлено на скриншоте ниже:

![all default_fact](https://github.com/user-attachments/assets/2fe367d1-8ed4-4a91-b47c-066ee9336499)

3. Воспользуйтесь подготовленным (используется `docker`) или создайте собственное окружение для проведения дальнейших испытаний.

docker run -dit --name centos7 pycontribs/centos:7 sleep 6000000

docker run -dit --name ubuntu pycontribs/ubuntu:latest sleep 6000000

4. Проведите запуск playbook на окружении из `prod.yml`. Зафиксируйте полученные значения `some_fact` для каждого из `managed host`.

Выполнение задания представлено на скриншоте ниже:

![some_fact prod](https://github.com/user-attachments/assets/6e9c3e39-35c6-4fa0-8f5a-b528aa733279)

5. Добавьте факты в `group_vars` каждой из групп хостов так, чтобы для `some_fact` получились значения: для `deb` — `deb default fact`, для `el` — `el default fact`.
6.  Повторите запуск playbook на окружении `prod.yml`. Убедитесь, что выдаются корректные значения для всех хостов.

Выполнение задания представлено на скриншоте ниже:

![some_fact prod izm](https://github.com/user-attachments/assets/d90577c0-2fad-4505-84ab-8c4ef35fff74)

7. При помощи `ansible-vault` зашифруйте факты в `group_vars/deb` и `group_vars/el` с паролем `netology`.
8. Запустите playbook на окружении `prod.yml`. При запуске `ansible` должен запросить у вас пароль. Убедитесь в работоспособности.

Выполнение заданий представлено на скриншотах ниже:

![ansible-vault1](https://github.com/user-attachments/assets/ac82aa61-dcd6-4cc7-b06d-75e8a0314b83)

![ansible-vault2](https://github.com/user-attachments/assets/62811569-2bd1-4fc4-9cdb-7db24cd5a85e)

9. Посмотрите при помощи `ansible-doc` список плагинов для подключения. Выберите подходящий для работы на `control node`.

Выполнение задания представлено на скриншоте ниже:
Здесь мы видим что нам подойдет плагин local

![local](https://github.com/user-attachments/assets/e33e5468-4476-4fb2-9ae7-37ebc8461349)

10. В `prod.yml` добавьте новую группу хостов с именем  `local`, в ней разместите localhost с необходимым типом подключения.
11. Запустите playbook на окружении `prod.yml`. При запуске `ansible` должен запросить у вас пароль. Убедитесь, что факты `some_fact` для каждого из хостов определены из верных `group_vars`.

![localhost](https://github.com/user-attachments/assets/12cb0904-a22c-482d-bba9-7b4b8947ab17)

12. Заполните `README.md` ответами на вопросы. Сделайте `git push` в ветку `master`. В ответе отправьте ссылку на ваш открытый репозиторий с изменённым `playbook` и заполненным `README.md`.
13. Предоставьте скриншоты результатов запуска команд.


---

### Как оформить решение задания

Выполненное домашнее задание пришлите в виде ссылки на .md-файл в вашем репозитории.

---


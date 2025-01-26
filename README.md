# OTUS
Описание стенда - Хост - Windows 10 + Hyper-V/VM CentOS10 Stream/Vagrand + Virtual box/CentOS8
Возникшие проблемы:
1. Проблемы с установкой virtualbox. Установка с репозитория невозможна, так как нет версии для CentOS10. Решение - изменение ссылки в репозитории на версию 9
2. Требуется библиотека libXt.so.6()(64bit). По умолчанию стоит более свежая версия библиотеки. Решение с символьными ссылками не подошло. Решение - удаление текущей версии, установка версии 6. Последствия - отвал графического интерфейса. Переустановка последней версии результата не дала
3. Проблема с подключению к репозиторию elrepo в ВМ CentOS8.
Решение:
sed -i s/mirror.centos.org/vault.centos.org/g /etc/yum.repos.d/CentOS-*.repo
sed -i s/^#.*baseurl=http/baseurl=http/g /etc/yum.repos.d/CentOS-*.repo
sed -i s/^mirrorlist=http/#mirrorlist=http/g /etc/yum.repos.d/CentOS-*.repo

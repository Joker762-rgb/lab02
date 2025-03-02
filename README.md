luka@luka-VirtualBox:~$ export GITHUB_USERNAME=Joker762-rgb
luka@luka-VirtualBox:~$ export GITHUB_EMAIL=Kuzmin2006.ru@yandex.ru
luka@luka-VirtualBox:~$ export GITHUB_TOKEN=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
luka@luka-VirtualBox:~$ alias edit=nano
luka@luka-VirtualBox:~$ cd ${GITHUB_USERNAME}/workspace
luka@luka-VirtualBox:~/Joker762-rgb/workspace$ source scripts/activate
luka@luka-VirtualBox:~/Joker762-rgb/workspace$ mkdir ~/.config
luka@luka-VirtualBox:~/Joker762-rgb/workspace$ cat > ~/.config/hub <<EOF
> github.com:
> - user: ${GITHUB_USERNAME}
> oauth_token: ${GITHUB_TOKEN}
> protocol: https
> EOF
luka@luka-VirtualBox:~/Joker762-rgb/workspace$ git config --global hub.protocol https
luka@luka-VirtualBox:~/Joker762-rgb/workspace$ mkdir projects/lab02 && cd projects/lab02
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ git init
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint:
hint: 	git config --global init.defaultBranch <name>
hint:
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint:
hint: 	git branch -m <name>
Инициализирован пустой репозиторий Git в /home/luka/Joker762-rgb/workspace/projects/lab02/.git/
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ git config --global user.name ${GITHUB_USERNAME}
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ git config --global user.email ${GITHUB_EMAIL}
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ git config -e --global
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab02.git
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ git pull origin master
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ touch README.md
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ git status
Текущая ветка: master

Еще нет коммитов

Неотслеживаемые файлы:
  (используйте «git add <файл>...», чтобы добавить в то, что будет включено в коммит)
	README.md

индекс пуст, но есть неотслеживаемые файлы
(используйте «git add», чтобы проиндексировать их)
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ git add README.md
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ git commit -m"added README.md"
[master (корневой коммит) c0e5570] added README.md
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 README.md
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ git push origin master
Username for 'https://github.com': Joker762-rgb
Password for 'https://Joker762-rgb@github.com': 
remote: Support for password authentication was removed on August 13, 2021.
remote: Please see https://docs.github.com/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ git pull origin master
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ git log
commit c0e557027e2f61919b2dfef3d8cb0f0d58ef9995 (HEAD -> master)
Author: Joker762-rgb <Kuzmin2006.ru@yandex.ru>
Date:   Sun Mar 2 16:44:30 2025 +0300

    added README.md
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ mkdir sources
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ mkdir include
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ mkdir examples
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ cat > sources/print.cpp <<EOF
> #include <print.hpp>
> void print(const std::string& text, std::ostream& out)
> {
> out << text;
> }
> void print(const std::string& text, std::ofstream& out)
> {
> out << text;
> }
> EOF
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ cat > include/print.hpp <<EOF
> #include <fstream>
> #include <iostream>
> #include <string>
> void print(const std::string& text, std::ofstream& out);
> void print(const std::string& text, std::ostream& out = std::cout);
EOF

luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ cat > include/print.hpp <<EOF
> #include <fstream>
> #include <iostream>
> #include <string>
> void print(const std::string& text, std::ofstream& out);
> void print(const std::string& text, std::ostream& out = std::cout);
> EOF
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ cat > examples/example1.cpp <<EOF
> #include <print.hpp>
> int main(int argc, char** argv)
> {
> print("hello");
> }
> EOF
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ cat > examples/example2.cpp <<EOF
> #include <print.hpp>
> #include <fstream>
> int main(int argc, char** argv)
> {
> std::ofstream file("log.txt");
> print(std::string("hello"), file);
> }
> EOF
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ edit README.md
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ git status
Текущая ветка: master
Неотслеживаемые файлы:
  (используйте «git add <файл>...», чтобы добавить в то, что будет включено в коммит)
	examples/
	include/
	sources/

индекс пуст, но есть неотслеживаемые файлы
(используйте «git add», чтобы проиндексировать их)
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ git add .
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ git commit -m"added sources"
[master 71a1cb3] added sources
 4 files changed, 26 insertions(+)
 create mode 100644 examples/example1.cpp
 create mode 100644 examples/example2.cpp
 create mode 100644 include/print.hpp
 create mode 100644 sources/print.cpp
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$ git push origin master
Username for 'https://github.com': Joker762-rgb
Password for 'https://Joker762-rgb@github.com': 
Перечисление объектов: 10, готово.
Подсчет объектов: 100% (10/10), готово.
При сжатии изменений используется до 12 потоков
Сжатие объектов: 100% (7/7), готово.
Запись объектов: 100% (9/9), 862 байтов | 862.00 КиБ/с, готово.
Всего 9 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
To https://github.com/Joker762-rgb/lab02.git
   29f8b94..773b90c  master -> master
luka@luka-VirtualBox:~/Joker762-rgb/workspace/projects/lab02$

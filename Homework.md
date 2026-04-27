**Part I**
1. Создайте пустой репозиторий на сервисе github.com (или gitlab.com, или bitbucket.com).</br>
**Вывод**:</br>
*Репозиторий создан*</br>
</br>

2. Выполните инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге.</br>
**Команда**:</br>
`git add README.md`</br>
`git commit -m"added README.md"`</br>
`git push origin master`</br>
**Вывод**:</br>
[master cbc713b] added README.md
 1 file changed, 1 insertion(+)
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Writing objects: 100% (3/3), 272 bytes | 272.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/JustACat3680/lab02
   742148f..cbc713b  master -> master
</br>

3. Создайте файл hello_world.cpp в локальной копии репозитория (который должен был появиться на шаге 2). Реализуйте программу Hello world на языке C++ используя плохой стиль кода. Например, после заголовочных файлов вставьте строку using namespace std;.</br>
**Команда**:</br>
`nano hello_world.cpp`</br>
**Вывод**:</br>
#include <iostream>
using namespace std;
int main()
{
    cout<<"Hello World"<<endl;
    return 0;
}
</br>

4. Добавьте этот файл в локальную копию репозитория.</br>
**Команда**:</br>
`git add hello_world.cpp`</br>
**Вывод**:</br>
*Файл добавлен*</br>
</br>

5. Закоммитьте изменения с осмысленным сообщением.</br>
**Команда**:</br>
`git commit -m"added hello_world.cpp"`</br>
**Вывод**:</br>
[master 2f23af1] added hello_world.cpp
 1 file changed, 7 insertions(+)
 create mode 100644 hello_world.cpp
</br>

6. Изменитьте исходный код так, чтобы программа через стандартный поток ввода запрашивалось имя пользователя. А в стандартный поток вывода печаталось сообщение Hello world from @name, где @name имя пользователя.</br>
**Команда**:</br>
`nano hello_world.cpp`</br>
**Вывод**:</br>
#include <iostream>
using namespace std;
int main()
{ 
    string name;
    cout<<"Input name: "; cin>>name;
    cout<<"Hello World from "<<name<<endl;
    return 0;
}

</br>

7. Закоммитьте новую версию программы. Почему не надо добавлять файл повторно git add?</br>
**Команда**:</br>
`git commit -am"edited hello_world.cpp"`</br>
**Вывод**:</br>
[master 4f89e1e] edited hello_world.cpp
 1 file changed, 3 insertions(+), 1 deletion(-)

</br>

8. Запуште изменения в удалёный репозиторий.</br>
**Команда**:</br>
`git push origin master`</br>
**Вывод**:</br>
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 2 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 412 bytes | 412.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/JustACat3680/lab02
   2f23af1..4f89e1e  master -> master
</br>

9. Проверьте, что история коммитов доступна в удалёный репозитории.</br>
**Вывод**:</br>
*История коммитов доступна*</br>
</br>

**Part II**

1. В локальной копии репозитория создайте локальную ветку patch1.</br>
**Команда**:</br>
`git checkout -b patch1`</br>
**Вывод**:</br>
Switched to a new branch 'patch1'</br>
</br>

2. Внесите изменения в ветке patch1 по исправлению кода и избавления от using namespace std;.</br>
**Команда**:</br>
`nano hello_world.cpp`</br>
**Вывод**:</br>
#include <iostream>
int main()
{
    std::string name;
    std::cout<<"Input name: "; std::cin>>name;
    std::cout<<"Hello World from "<<name<<std::endl;
    return 0;
}
</br>

3. commit, push локальную ветку в удалённый репозиторий.</br>
**Команда**:</br>
`git commit -am"edited hello_world.cpp"`</br>
`git push origin patch1`</br>
**Вывод**:</br>
[patch1 9be62df] edited hello_world.cpp
 1 file changed, 3 insertions(+), 4 deletions(-)
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 2 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 410 bytes | 410.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote: 
remote: Create a pull request for 'patch1' on GitHub by visiting:
remote:      https://github.com/JustACat3680/lab02/pull/new/patch1
remote: 
To https://github.com/JustACat3680/lab02
 * [new branch]      patch1 -> patch1
</br>

4. Проверьте, что ветка patch1 доступна в удалёный репозитории.</br>
**Вывод**:</br>
*Ветка patch1 доступна*</br>
</br>

5. Создайте pull-request patch1 -> master.</br>
**Вывод**:</br>
*Pull-request создан*</br>
</br>

6. В локальной копии в ветке patch1 добавьте в исходный код комментарии.</br>
**Команда**:</br>
`nano hello_world.cpp`</br>
**Вывод**:</br>
#include <iostream>
int main()
{
    std::string name;
    std::cout<<"Input name: "; std::cin>>name; //ввод имени
    std::cout<<"Hello World from "<<name<<std::endl; //вывод в консоль
    return 0;
}
</br>

7. commit, push.</br>
**Команда**:</br>
`git commit -am"edited hello_world.cpp"`</br>
`git push origin patch1`</br>
**Вывод**:</br>
[patch1 362b664] edited hello_world.cpp
 1 file changed, 2 insertions(+), 2 deletions(-)
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 2 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 385 bytes | 385.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/JustACat3680/lab02
   9be62df..362b664  patch1 -> patch1
</br>

8. Проверьте, что новые изменения есть в созданном на шаге 5 pull-request</br>
**Вывод**:</br>
*Изменения присутствуют*</br>
</br>

9. В удалённый репозитории выполните слияние PR patch1 -> master и удалите ветку patch1 в удаленном репозитории.</br>
**Вывод**:</br>
*Выполнено слияние pull-request, ветка patch1 удалена*</br>
</br>

10. Локально выполните pull.</br>
**Команда**:</br>
`git checkout master`</br>
`git pull origin master`</br>
**Вывод**:</br>
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (1/1), 897 bytes | 897.00 KiB/s, done.
From https://github.com/JustACat3680/lab02
 * branch            master     -> FETCH_HEAD
   4f89e1e..6ce8791  master     -> origin/master
Updating 4f89e1e..6ce8791
Fast-forward
 hello_world.cpp | 7 +++----
 1 file changed, 3 insertions(+), 4 deletions(-)
</br>

11. С помощью команды git log просмотрите историю в локальной версии ветки master.</br>
**Команда**:</br>
`git log`</br>
**Вывод**:</br>
commit 6ce879138570ad13515f23f04cf419bf1da126e9 (HEAD -> master, origin/master)
Merge: 4f89e1e 362b664
Author: JustACat3680 <justacat3680@gmail.com>
Date:   Thu Apr 16 09:39:12 2026 +0300

    Merge pull request #2 from JustACat3680/patch1

    edited hello_world.cpp

commit 362b66411f339ec5b84b2f0655290f98feb7594f (origin/patch1, patch1)
Author: JustACat3680 <justacat3680@gmail.com>
Date:   Thu Apr 16 09:32:25 2026 +0300

    edited hello_world.cpp

commit 9be62df6a77b1d84c574736aa690d88f1deedf71
Author: JustACat3680 <justacat3680@gmail.com>
Date:   Thu Apr 16 09:06:00 2026 +0300

    edited hello_world.cpp

commit 4f89e1e981010969f4d0e22a1024d60e9d8f6f6d
Author: JustACat3680 <justacat3680@gmail.com>
Date:   Thu Apr 2 10:07:22 2026 +0300

    edited hello_world.cpp

commit 2f23af15d87d4e4152ed4423bf75d181853e953f
Author: JustACat3680 <justacat3680@gmail.com>
Date:   Thu Apr 2 09:47:28 2026 +0300

    added hello_world.cpp

commit cbc713b0677dde4b27fec7b4f9234a76c2cfe9ce
Author: JustACat3680 <justacat3680@gmail.com>
Date:   Thu Apr 2 09:31:40 2026 +0300

    added README.md
(END)
</br>

12. Удалите локальную ветку patch1.</br>
**Команда**:</br>
`git branch -d patch1`</br>
**Вывод**:</br>
Deleted branch patch1 (was 362b664).
</br>

**Part III**
1. Создайте новую локальную ветку patch2.</br>
**Команда**:</br>
`git checkout -b patch2`</br>
**Вывод**:</br>
Switched to a new branch 'patch2'
</br>

2. Измените code style с помощью утилиты clang-format. Например, используя опцию -style=Mozilla.</br>
**Команда**:</br>
`clang-format -style=Mozilla -dump-config > .clang-format`</br>
`clang-format -i hello_world.cpp`</br>
**Вывод**:</br>
#include <iostream>
int
main()
{
  std::string name;
  std::cout << "Input name: ";
  std::cin >> name;                                      // ввод имени
  std::cout << "Hello World from " << name << std::endl; // вывод в консоль
  return 0;
}
</br>

3. commit, push, создайте pull-request patch2 -> master.</br>
**Команда**:</br>
`git commit -am"edited hello_world.cpp"`</br>
`git push origin patch2`</br>
**Вывод**:</br>
[patch2 61aa44b] edited hello_world.cpp
 1 file changed, 7 insertions(+), 5 deletions(-)
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 2 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 464 bytes | 464.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote: 
remote: Create a pull request for 'patch2' on GitHub by visiting:
remote:      https://github.com/JustACat3680/lab02/pull/new/patch2
remote: 
To https://github.com/JustACat3680/lab02
 * [new branch]      patch2 -> patch2
</br>

4. В ветке master в удаленном репозитории измените комментарии, например, расставьте знаки препинания, переведите комментарии на другой язык.</br>
**Вывод**:</br>
#include <iostream>
int main()
{
    std::string name;
    std::cout<<"Input name: "; std::cin>>name; //input
    std::cout<<"Hello World from: "<<name<<std::endl; //output
    return 0;
}
</br>

5. Убедитесь, что в pull-request появились конфликтны.</br>
**Вывод**:</br>
*Конфликты появились:*</br>
This branch has conflicts that must be resolved</br>
</br>

6. Для этого локально выполните pull + rebase (точную последовательность команд, следует узнать самостоятельно). Исправьте конфликты.</br>
**Команда**:</br>
`git pull --rebase origin master`</br>
`nano hello_world.cpp`</br>
`git add hello_world.cpp`</br>
`git rebase --continue`</br>
**Вывод**:</br>
#include <iostream>
int main()
{
<<<<<<< HEAD
    std::string name;
    std::cout<<"Input name: "; std::cin>>name; //input
    std::cout<<"Hello World from: "<<name<<std::endl; //output
    return 0;
=======
  std::string name;
  std::cout << "Input name: ";
  std::cin >> name;                                      // ввод имени
  std::cout << "Hello World from " << name << std::endl; // вывод в консоль
  return 0;
>>>>>>> 184b041 (edited hello_world.cpp)
}

remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 1013 bytes | 337.00 KiB/s, done.
From https://github.com/JustACat3680/lab02
 * branch            master     -> FETCH_HEAD
   6ce8791..46ed7b1  master     -> origin/master
Auto-merging hello_world.cpp
CONFLICT (content): Merge conflict in hello_world.cpp
error: could not apply 61aa44b... edited hello_world.cpp
hint: Resolve all conflicts manually, mark them as resolved with
hint: "git add/rm <conflicted_files>", then run "git rebase --continue".
hint: You can instead skip this commit: run "git rebase --skip".
hint: To abort and get back to the state before "git rebase", run "git rebase --abort".
hint: Disable this message with "git config advice.mergeConflict false"
Could not apply 61aa44b... edited hello_world.cpp

Successfully rebased and updated refs/heads/patch2.
</br>

7. Сделайте force push в ветку patch2</br>
**Команда**:</br>
`git push --force origin patch2`</br>
**Вывод**:</br>
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 2 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 327 bytes | 327.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/JustACat3680/lab02
   46ed7b1..6c5131b  patch2 -> patch2
</br>

8. Убедитель, что в pull-request пропали конфликтны.</br>
**Вывод**:</br>
*В pull-request конфликтов нет*</br>
</br>

9. Вмержите pull-request patch2 -> master.</br>
**Команда**:</br>
`git checkout master`</br>
`git merge patch2`</br>
`git push origin master`</br>
**Вывод**:</br>
Switched to branch 'master'
Your branch is up to date with 'origin/master'.

Updating 46ed7b1..6c5131b
Fast-forward
 hello_world.cpp | 3 ++-
 1 file changed, 2 insertions(+), 1 deletion(-)

Total 0 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/JustACat3680/lab02
   46ed7b1..6c5131b  master -> master
</br>

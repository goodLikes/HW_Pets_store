# Итоговая контрольная работа

## Информация о проекте
- **Цель**: Организация системы учета для питомника с домашними и вьючными животными.

## Как сдавать проект
1. Создать общедоступный репозиторий (GitHub, GitLab или Bitbucket).
2. Вести разработку в репозитории, использовать пул-реквесты.
3. Программа должна работать без ошибок.

## Задание

1. **Создание файлов**:
   - Использовать команду `cat` для создания двух файлов:
     - `Домашние животные`: заполнить собаками, кошками, хомяками.
     - `Вьючные животные`: заполнить лошадьми, верблюдами, ослами.
   - Объединить файлы и просмотреть содержимое.
   - Переименовать файл в `Друзья человека`.

2. **Создание директории**:
   - Переместить файл в новую директорию.

3. **Работа с репозиторием MySQL**:
   - Подключить дополнительный репозиторий MySQL.
   - Установить любой пакет из репозитория.

4. **Управление пакетами**:
   - Установить и удалить deb-пакет с помощью `dpkg`.

5. **История команд**:
   - Выложить историю команд в терминале Ubuntu.

6. **Диаграмма классов**:
   - Нарисовать диаграмму с:
     - Родительским классом
     - Классами: домашние животные (собаки, кошки, хомяки) и вьючные животные (лошади, верблюды, ослы).

7. **Создание базы данных**:
   - Создать базу данных “Друзья человека” в MySQL.

8. **Создание таблиц**:
   - Создать таблицы с иерархией из диаграммы в БД.

9. **Заполнение таблиц**:
   - Заполнить низкоуровневые таблицы именами животных, командами и датами рождения.

10. **Удаление записей**:
    - Удалить верблюдов и объединить таблицы лошадей и ослов.

11. **Создание новой таблицы**:
    - Создать таблицу “молодые животные” (возраст: >1 год и <3 года).
    - Подсчитать возраст животных с точностью до месяца.

12. **Объединение таблиц**:
    - Объединить все таблицы в одну, сохраняя ссылки на старые таблицы.

13. **Создание класса с инкапсуляцией и наследованием**:
    - Реализовать класс в соответствии с диаграммой.

14. **Программа реестра домашних животных**:
    - Реализовать функционал:
      1. Завести новое животное.
      2. Определить животное в правильный класс.
      3. Показать список команд.
      4. Обучить животное новым командам.
      5. Реализовать навигацию по меню.

15. **Создание класса Счетчик**:
    - Метод `add()` увеличивает значение переменной на 1 при добавлении животного.
    - Реализовать работу в блоке `try-with-resources`, выбрасывая исключение при неправильном использовании.


# Решение

## Шаги 1-2

1. **Перейти в директорию проекта**:
   ```bash
   leej@leej-VirtualBox:~$ cd Pitomnik2/
   ```

2. **Создать файл с домашними животными**:
   ```bash
   leej@leej-VirtualBox:~/Pitomnik2$ cat > Pets.txt
   Собака
   Кошка
   Хомяк
   ```

3. **Создать файл с вьючными животными**:
   ```bash
   leej@leej-VirtualBox:~/Pitomnik2$ cat > PackAnimals.txt
   Лошадь
   Верблюд
   Оcел
   ```

4. **Объединить файлы и создать новый файл**:
   ```bash
   leej@leej-VirtualBox:~/Pitomnik2$ cat Pets.txt PackAnimals.txt > Animals.txt
   ```

5. **Просмотреть содержимое нового файла**:
   ```bash
   leej@leej-VirtualBox:~/Pitomnik2$ cat Animals.txt
   Собака
   Кошка
   Хомяк
   Лошадь
   Верблюд
   Оcел
   ```

6. **Переименовать файл**:
   ```bash
   leej@leej-VirtualBox:~/Pitomnik2$ mv Animals.txt HumanFriends.txt
   ```

7. **Проверить файлы в директории**:
   ```bash
   leej@leej-VirtualBox:~/Pitomnik2$ ls
   HumanFriends.txt  PackAnimals.txt  Pets.txt
   ```

8. **Создать новую директорию**:
   ```bash
   leej@leej-VirtualBox:~/Pitomnik2$ mkdir PetsDirectory
   ```

9. **Переместить файл в новую директорию**:
   ```bash
   leej@leej-VirtualBox:~/Pitomnik2$ mv HumanFriends.txt PetsDirectory/
   ```

10. **Перейти в директорию с файлами**:
    ```bash
    leej@leej-VirtualBox:~/Pitomnik2$ cd PetsDirectory/
    ```

11. **Проверить содержимое директории**:
    ```bash
    leej@leej-VirtualBox:~/Pitomnik2/PetsDirectory$ ls
    HumanFriends.txt
    ```

## Шаг 3: Подключение и установка MySQL

1. **Обновить пакеты**:
   ```bash
   leej@leej-VirtualBox:~/Pitomnik2/PetsDirectory$ sudo apt-get update
   ```

2. **Установить MySQL сервер**:
   ```bash
   leej@leej-VirtualBox:~/Pitomnik2/PetsDirectory$ sudo apt-get install mysql-server
   ```

3. **Проверить установленную версию MySQL**:
   ```bash
   leej@leej-VirtualBox:~/Pitomnik2/PetsDirectory$ mysql --version
   ```

4. **Установить дополнительный пакет (cowsay)**:
   ```bash
   leej@leej-VirtualBox:~/Pitomnik2/PetsDirectory$ sudo apt-get install cowsay
   ```

5. **Использовать cowsay**:
   ```bash
   leej@leej-VirtualBox:~/Pitomnik2/PetsDirectory$ cowsay "Здарова отец!"
   ```

6. **Удалить cowsay**:
   ```bash
   leej@leej-VirtualBox:~/Pitomnik2/PetsDirectory$ sudo apt-get remove cowsay
   ```

## Шаг 5: История команд

1. **Сохранить историю команд в файл**:
   ```bash
   leej@leej-VirtualBox:~/Pitomnik2/PetsDirectory$ history > history.txt
   ```

## Шаг 6: Создание базы данных MySQL

1. **Создать базу данных**:
   ```sql
   mysql> CREATE DATABASE HumanFriends;
   ```

2. **Использовать созданную базу данных**:
   ```sql
   mysql> USE HumanFriends;
   ```

3. **Создать таблицы**:
   - **Таблица домашних животных**:
     ```sql
     mysql> CREATE TABLE Pets (
         ID INT AUTO_INCREMENT PRIMARY KEY,
         Name VARCHAR(50),
         Type VARCHAR(20),
         BirthDate DATE,
         Commands TEXT
     );
     ```

   - **Таблица вьючных животных**:
     ```sql
     mysql> CREATE TABLE PackAnimals (
         ID INT AUTO_INCREMENT PRIMARY KEY,
         Name VARCHAR(50),
         Type VARCHAR(20),
         BirthDate DATE,
         Commands TEXT
     );
     ```

4. **Заполнение таблиц**:
   - **Заполнение таблицы домашних животных**:
     ```sql
     mysql> INSERT INTO Pets (Name, Type, BirthDate, Commands) VALUES
         ('Fido', 'Dog', '2020-01-01', 'Sit, Stay, Fetch'),
         ('Whiskers', 'Cat', '2019-05-15', 'Sit, Pounce'),
         ('Hammy', 'Hamster', '2021-03-10', 'Roll, Hide'),
         ('Buddy', 'Dog', '2018-12-10', 'Sit, Paw, Bark'),
         ('Smudge', 'Cat', '2020-02-20', 'Sit, Pounce, Scratch'),
         ('Peanut', 'Hamster', '2021-08-01', 'Roll, Spin'),
         ('Bella', 'Dog', '2019-11-11', 'Sit, Stay, Roll'),
         ('Oliver', 'Cat', '2020-06-30', 'Meow, Scratch, Jump');
     ```

   - **Заполнение таблицы вьючных животных**:
     ```sql
     mysql> INSERT INTO PackAnimals (Name, Type, BirthDate, Commands) VALUES
         ('Thunder', 'Horse', '2015-07-21', 'Trot, Canter, Gallop'),
         ('Sandy', 'Camel', '2016-11-03', 'Walk, Carry Load'),
         ('Eeyore', 'Donkey', '2017-09-18', 'Walk, Carry Load, Bray'),
         ('Storm', 'Horse', '2014-05-05', 'Trot, Canter'),
         ('Dune', 'Camel', '2018-12-12', 'Walk, Sit'),
         ('Burro', 'Donkey', '2019-01-23', 'Walk, Bray, Kick'),
         ('Blaze', 'Horse', '2016-02-29', 'Trot, Jump, Gallop'),
         ('Sahara', 'Camel', '2015-08-14', 'Walk, Run');
     ```

5. **Удаление верблюдов**:
   ```sql
   mysql> DELETE FROM PackAnimals WHERE Type = 'Camel';
   ```

6. **Объединение таблиц**:
   ```sql
   mysql> CREATE TABLE CombinedAnimals AS
       SELECT * FROM Pets
       UNION ALL
       SELECT * FROM PackAnimals;
   ```

7. **Создание таблицы молодых животных**:
   ```sql
   mysql> CREATE TABLE YoungAnimals AS
       SELECT
           ID,
           Name,
           Type,
           BirthDate,
           Commands,
           FLOOR(DATEDIFF(CURDATE(), BirthDate)/30) AS AgeInMonths
       FROM
           CombinedAnimals
       WHERE
           DATEDIFF(CURDATE(), BirthDate) BETWEEN 365 AND 1095;
   ```

8. **Создание итоговой таблицы**:
   ```sql
   mysql> CREATE TABLE AllAnimals AS
       SELECT
           'Pets' AS Category,
           ID,
           Name,
           Type,
           BirthDate,
           Commands
       FROM
           Pets
       UNION ALL
       SELECT
           'PackAnimals' AS Category,
           ID,
           Name,
           Type,
           BirthDate,
           Commands
       FROM
           PackAnimals
       UNION ALL
       SELECT
           'CombinedAnimals' AS Category,
           ID,
           Name,
           Type,
           BirthDate,
           Commands
       FROM
           CombinedAnimals
       UNION ALL
       SELECT
           'YoungAnimals' AS Category,
           ID,
           Name,
           Type,
           BirthDate,
           Commands
       FROM
           YoungAnimals;
   ```

## Пользователи, роли, доступы, должности, контакты, приглашения и иже с ним.

Проблема 1: требуется более сложное разграничение доступов?
На одном проекте номер телефона ххх будет у нас оставлять замечания, а на другом проекте - быть исполнителем работ.
При этом если я технадзор, то только я и создатель шахматки можем создавать замечания и закрывать их. Другие замечания просматривают.
При этом если я исполнитель, то только я и создатель шахматки можем создавать работы и закрывать их. Другие работы просматривают.
Наряды и отчеты вообще никто, кроме пользователя, не видит.

Проблема 2: сквозные данные по ФИО - путают пользователяю, потому что это коллективное редактирование.
С точки зрения системы, оно должно быть 

Проблема 3: чувствительные данные - я может даже и не хочу, чтобы мои данные кто-то видел, кроме начальника-прораба.

Что такое есть должность в нашей системе?
Не более, чем комментарий сейчас. Привязать разграничение доступов к должности можно, но нужно ли?
Так или иначе, лучше словарь должностей завести, если эта должность так уж нужна.
Нужен ли нам внутренний комментарий по всем нашим исполнителям?




Ролевая модель в системе на текущий момент отсутствует. То есть:
Пользователи никак не отличаются в системе друг от друга, даже если обладают разными должностями (прораб, начальник участка, технадзор, бригадир, мастер участка и др.). Во-первых, их функции могут меняться со временем, во-вторых иногда они совмещают разную деятельность. Например, Пользователь может быть 
одновременно прорабом и технадзором, не говоря уже о разных ролях на разных объектах.

Основные функции, доступные любому пользователию в своем аккаунте - CRUD-операции для шахматок, нарядов/отчетов/реестров, справочников (работы, технадзоры, исполнители), замечаний, настройка (аккаунт, статусы, виды работ).

При этом надо понимать, что пользователь при формировании реестров на выплату все равно узнает ФИО работников. А вот работникам знать друг друга совсем не обязательно?

Могу ли я как пользователь видеть чувствительные данные исполнителей в шахматках, к которым у меня доступ на чтение? На редактирование?


| Кто | Что хочет | Для чего |
|-----|------|-------|
||||
|| Работа со своими шахматками ||
||||
| User | (!) Видеть полные ФИО своих исполнителей        | Формирование корректных нарядов, реестров, других документов |
| User | (!) Не вводить вручную ФИО своих исполнителей   | Ускорение и упрощение работы с продуктом                     |
| User | Совершать CRUD-операции над справочниками (работ, технадзоров, исполнителей) | Выполнение базовых действий с шахматкой, замечаниями, нарядами |
|      | - Изменять данные исполнителей                | Поддержка актуальной контактной информации - исполнители       |
|      | - Изменять данные технадзоров                 | Поддержка актуальной контактной информации - технадзор         |
| User | Совершать CRUD-операции над шахматками        | Базовая работа с шахматкой                                     |
| User | Совершать CRUD-операции над нарядами          | Базовая работа с нарядами                                      |
| User | Совершать CRUD-операции над замечаниями       | Базовая работа с замечаниями                                   |
| User | (!) НЕ изменяемость моих шахматок третьими лицами  | Не путаться, не терять реальные данные и не подозревать систему в скомпрометирвоанности |
| User | (!) Изменяемость моих шахматок третьими лицами     | Актуализация данных |
| User | (!) НЕ изменяемость моих замечаний третьими лицами | Не путаться, не терять реальные данные и не подозревать систему в скомпрометирвоанности |
| User | (!) Изменяемость моих замечаний третьими лицами    | Актуализация данных |
| User | Давать возможность оставлять замечания как технадзору, так и исполнителю (бригадиру, например) | Быстрое заполнение справочников                         |
| User | Давать возможность редактировать работы как исполнителю, так и технадзору (бригадиру, например) | Быстрое заполнение справочников                         |
| User | Изменять свои пользовательские настройки           | Поддержка актуальной контактной информации (своей) и персонализация |
| User | НЕ изменяемость моих настроек третьими лицами      | Не путаться, не терять реальные данные и не подозревать систему в скомпрометированности |
| User | Импортировать контакты из телефонной книги         | Быстрое заполнение справочников                         |
| User | Назначать себя исполнителем                        | Для удобства                                            |
| User | Назначать себя тезнадзором                         | Для удобства                                            |
| User | Создавать dummy-исполнителей                       | Для операционного учета, когда телефон человек неизвестен или его ФИО неизвестны? |
|
||||
|| Смотрю чужие шахматки - просмотр ||
||||
| User | НЕ изменяемость моих настроек третьими лицами | Не путаться, не терять реальные данные и не подозревать систему в скомпрометирвоанности |

||||
|| Смотрю чужие шахматки - редактирование ||
||||

||||
|| Другие смотрям мои шахматки - просмотр ||
||||
||||
|| Другие смотрям мои шахматки - редактирование ||
||||
| Non-user | НЕ видимость моих данных никому, кроме непосредственного руководителя/прораба !!! | Сохранение конфиденциальности        |
| Non-user | Видимость моих данных всем                                                    !!! | Оперативное решение рабочих вопросов |
| System | Обеспечить возможность передавать все данные пользователей третьим лицам в неограниченном количестве | Юридическая чистота |

Пользователь всегда может менять свои системные настройки
Пользователь никогда может менять чужие системные настройки
При этом пользователь хочет всегда помечать другие телефоны так, как удобно ему. При этом чем ближе этот никнейм к реальному имени, тем меньше проблем с документами.
Но и бегать уточнять, как кого зовут, пользователь не хочет. Он хочет обозвать исполнителя как угодно. Потому через интеграцию с 1С надо нужны будут реальные имена.
Я могу хотеть дать возможность исполнителю вносить правки в работы на шахматке, но не вносить в замечания
Я могу хотеть дать возможность технадзорв вносить правки в замечния на шахматке, но не вносить в работы
Корректировать замечания может только их создатель или создатель шахматки.

1. Create-browse-edit-delete their own chessboards and all the dictinaries and settings (originated from theselves!)  
2. Users can never create-browse-edit-delete the others' chessboards, dictionaries and settings.  
3. Sometimes, when an access is granted, users can browse others' chessboards. But not setting, or dictionary, or others' access.  
4. Sometimes, when an access is granted, users can edit the others' chessboards. But not setting, or dictionary, or others' access.  
5. ASDF
6. Edit their own chessboards! And never others' chessboards.
7. Assign jobs/orders to others / to themselves
8. Assign tech.check to others / to themselves
9. Give right to view data
10. Give right to edit data
11. Browse the site-manager-view

# Users and Roles

There are different roles in the system:

1. A foreman / construction site manager
2. A technical supervisioner
3. A workman  

All of them are able to:

1. Create-browse-edit-delete their own chessboards and all the dictinaries and settings (originated from theselves!)  
2. Users can never create-browse-edit-delete the others' chessboards, dictionaries and settings.  
3. Sometimes, when an access is granted, users can browse others' chessboards. But not setting, or dictionary, or others' access.  
4. Sometimes, when an access is granted, users can edit the others' chessboards. But not setting, or dictionary, or others' access.  
5. ASDF
6. Edit their own chessboards! And never others' chessboards.
7. Assign jobs/orders to others / to themselves
8. Assign tech.check to others / to themselves
9. Give right to view data
10. Give right to edit data
11. Browse the site-manager-view

LEFT assigns a job to UPPER

| ...     | foreman | tech | workman |
|---------|---------|------|---------|
| foreman |    +    |      |    +    |
| tech    |         |      |    +    |
| workman |         |      |    +    |

If two workmen are given the rights to edit chessboard, and one of them deleted some stuff, for example, the list of works, what will user do?

Restoration of cheesboard!  
Logs of versions!

And still, we shall not give an opportunity to anyone to alter dictionaries, such as Workman list, TechSV list, and still - how can two foremen become friends of get access to one another's chessboards?

- via links
- via access

What can and can not a foreman (ordinary user) do:

| Feature | Foreman |
|----|-|
| | |

HAVE:

- Creating accounts for Workmen and Techmen - without any SMS confirmations.
- Account has fields: Name, Surname, Middlename, Phone number, email
- We do not want the user to scrupulously write down all his wormen's full names. But for users they are obligatory.
- What about state-models - for invitations and for accounts.

ALTERNATIVES:

- Creating not accounts but rather a handbook?
- ~~Asking everyone for confirmation~~

PROBLEMS:

- A user is able to insert incorrect telephone number
- A user is NOT able to correct neither phone number nor name
- What is "a position"?
- user fulfills only 1 field, and system decided what it is on its own.
- Whenever someone is registered in system (on his own or via invitation link = access granted) his name in almost any case will be changed - through the entire system.
- previous user can loose in their contacts! User is confused
- The system cannot work with semantics of the given string and will always think that it is, for example, just Middle name. incorrect parsing and lost of semantics
- We can loose the real data, if firstly name was entered correctly and after that substituted with dummy data. Data loss

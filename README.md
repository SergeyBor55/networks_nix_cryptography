## Тест на знание команд nix систем, компьютерных сетей, криптографии, СУБД MSSQL Server, SQL.
### Тест на знание команд nix систем
1. Какой командой можно посмотреть процессы запущенные от имени текущего пользователя;
* **ps -u**
2. Как посмотреть TOP процессов на машине;
* **Top -b –o +%MEM head –n 22**
3. Что показывает параметр load average? Значение параметра зависит от количества ядер процессора или от количества потоков? При каком значении считается, что машина загружена?
* **Load average показывает среднее значение загрузки процессора на временных участках (1, 5, 15 минут). Значение параметров зависит от количества потоков, а ядра это лимит по нагрузке. Если на одноядерной системе значение load average превышающее 1.00 на 5-ом или 15-ом минутном интервале, то машина перегружена. Если среднее значение постоянно превышает 0.70 следует выяснить причину такого поведения и устранить.**
4. Как посмотреть список файлов в текущей директории?
* **ls**
5. Какой командой можно дать права на исполнение файла всем пользователям?
* **chmod a+x file**
### Тест аля сеть

1. Как выяснить поднят порт на удаленном хосту, какой командой?
* **telnet ip-адрес порт**

2. Есть команда tracert, что с помощью данной команды можно выяснить?
* **Определить маршрут, по которому проходит пакет до заданного узла. Показывает время прохождения пакета до транзитных и конечного узла. Диагностика сети**

3. Ниже представлен результат трассировки. Что значат звездочки на 2-ом прыжке? Что значат большие тайминги на 4-ом прыжке? Что значат звездочки 6, 7, 8 прыжке?

> traceroute to 194.85.126.4 (194.85.126.4), 30 hops max, 40 byte packets

> 1 DCB-Core.net.dalcombank.ru (192.168.145.1) 0.901 ms 0.860 ms 1.214 ms

> 2 dcb-lcl-gw.asia-com.ru (79.171.112.33) * * 1.170 ms

> 3 kbk15.kbk26.transtelecom.net (217.150.58.186) 2.245 ms 2.238 ms 2.220 ms

> 4 ZapSibTTK2-gw.transtelecom.net (217.150.59.117) 225.888 ms 225.948 ms 225.932 ms

> 5 gw-billingovyjj-center-2.ll-nsk.zsttk.ru (80.89.132.50) 65.952 ms 65.945 ms 67.458 ms

> 6 * * *

> 7 * * *

> 8 * * *
* **Звёдочки на втором прыжке означают, что команда tracert не дождалась ответа от узла за определённый интервал времени. Большой тайминг на 4 прыжке может означать загруженность канала. Если канал не загружен необходимо проверить скорость скачивания с сервера по ftp/http, если плохая, проблема в соединении с провайдером. Если скорость скачивания хорошая и канал не загружен, значит проблема дольше по маршруту. Звёздочки в 6,7,8 прыжках говорят о том что ответ от удалённого узла не получен.**
### Тест криптография

1. Симметричное и ассиметричное шифрование, в чем разница?
* **В асимметричном шифровании используется два пароля - один открытый (публичный) и один закрытый (секретный).Такие алгоритмы шифрования позволяют свободно распространять пароль (ключ) по сети, так как без второго ключа невозможно получить исходное сообщение. В симметричном шифровании используется всего один пароль, чтобы получить исходный текст, используется этот же пароль, но с алгоритмом дешифрования**
2. Преимущества/недостатки ассиметричного шифрования
* **В случае с асимметричным шифрованием, становится несколько проще в плане хранения паролей, так как секретный ключ нет необходимости передавать кому-либо. Достаточно, чтобы его знал только один человек или сервер. Так же вопрос взлома пароля становится проще, так как сервер в любой момент может сменить пару ключей и разослать всем созданный открытый пароль. Однако, асимметричное шифрование более "тяжелое", другими словами, требует больше ресурсов компьютера. Так же есть ограничения на сам процесс генерации ключей (их еще нужно подобрать).**
3. Открытый и секретный ключ для чего используются?
* **Открытый ключ отсылается всем людям, закрытый же ключ остается на стороне сервера или другого приемника. Ключи равноценные, так как зашифрованное сообщение одним из ключей можно расшифровать только с помощью другого ключа**
### Имеются две таблицы: 
### create table department
(id number(10), name (varchar(100))
### create table employee
(id number(10), department_id number(10),chief_id number(10), name varchar(100),salary numer(10))

### Задача:(решение в снимке экрана)
Вывести название отделов и максимальную заработную плату в этих отделах

# homework6
выполняем vagrant up, он все делает по сжатию автоматом.
после выполнения заходим на vagrant ssh
в провижен скрипте указано что
otus1 - lzjb
otus2 - lz4
otus3 - gzip-9
otus4 - zle
так же скрипт автоматом наполняет файловые системы одним колличеством
проверяем
zfs list
zfs get all | grep compressratio | grep -v ref
алгоритм gzip-9 самый эффективный по сжатию


далее выполняем руками
wget -O archive.tar.gz --no-check-certificate 'https://drive.usercontent.google.com/download?id=1MvrcEp-WgAQe57aDEzxSRalPAwbNN1Bb&export=download'

tar -xzvf archive.tar.gz

zpool import -d zpoolexport/ otus

Запрос сразу всех параметром файловой системы: zfs get all otus

Работа со снапшотом, поиск сообщения от преподавателя
качаем
wget -O otus_task2.file --no-check-certificate https://drive.usercontent.google.com/download?id=1wgxjih8YZ-cqLqaZVa0lA3h3Y029c3oI&export=download
восстанавливаем
zfs receive otus/test@today < otus_task2.file
ищем
find /otus/test -name "secret_message"
открываем
cat /otus/test/task1/file_mess/secret_message
вывод = https://otus.ru/lessons/linux-hl/

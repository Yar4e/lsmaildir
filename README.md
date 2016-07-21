# lsmaildir
BASH сценарий, выводящий в человекочитаемом виде русскоязычные названия директорий maildir imap.

Если с англоязычными именами директорий в maildir проблем нет - отображаются они в точно так-же как и в почтовом клиенте, то с русскоязычными именами всё не так просто. Например, директория "Отправленные" в maildir -  &BB4EQgQ,BEAEMAQyBDsENQQ9BD0ESwQ1-. Дело в том, что imap использует модифицированную кодировку UTF-7 для именования директорий. Для того, чтобы эти имена стали человекочитаемы, нужно привести их к стандарту UTF-7 и перевести в UTF-8. Для этой цели, я написал небольшой сценарий, который производит это конвертирование и сопоставляет оригинальные и человекочитаемые имена файлов. Пример:

    $ lsmaildir
    Archives             Archives
    Archives.2013        Archives.2013
    Archives.2014        Archives.2014
    Нежелательная почта  &BB0ENQQ2BDUEOwQwBEIENQQ7BEwEPQQwBE8- &BD8EPgRHBEIEMA-
    Отправленные         &BB4EQgQ,BEAEMAQyBDsENQQ9BD0ESwQ1-
    Исходящие            &BBgEQQRFBD4ENARPBEkEOAQ1-
    Черновики            &BCcENQRABD0EPgQyBDgEOgQ4-
    Шаблоны              &BCgEMAQxBDsEPgQ9BEs-
    Удаленные            &BCMENAQwBDsENQQ9BD0ESwQ1-
    INBOX                INBOX

Выполнять сценарий можно как непосредственно в директории maildir, что иллюстрирует приведённый выше пример, так и указывая сценарию путь к этой директории в качестве аргумента:

    $ lsmaildir ~/offlineimap/maildirs/yar4e/
    Archives             Archives
    Archives.2013        Archives.2013
    Archives.2014        Archives.2014
    Нежелательная почта  &BB0ENQQ2BDUEOwQwBEIENQQ7BEwEPQQwBE8- &BD8EPgRHBEIEMA-
    Отправленные         &BB4EQgQ,BEAEMAQyBDsENQQ9BD0ESwQ1-
    Исходящие            &BBgEQQRFBD4ENARPBEkEOAQ1-
    Черновики            &BCcENQRABD0EPgQyBDgEOgQ4-
    Шаблоны              &BCgEMAQxBDsEPgQ9BEs-
    Удаленные            &BCMENAQwBDsENQQ9BD0ESwQ1-
    INBOX                INBOX

Опция -h или --help показывает лаконичное описание. 

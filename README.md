# yandex-s3-upload
sh for uploading file to s3 of yandex cloud


### А почему? 
Другие скрипты от aws не работают с яндексом?  
Все именно все так, как в скрипте? Ведь по AWS Signature Version 4 нужно делать по другому?  
Подсчет хэша идет не логично?  
Дата не соответствует документации?   
Не используются заголовки которые должны использоваться при авторизации с aws v4?  
#### Ответ:
Потому что это яндекс. Работает в таком виде - и слава богу. В документации у них на текущую дату (06.09.2021) полная ересь не совпадающая с реальностью. Со временем может поправят.


### Как использовать? 
Кидаете в папку sh скрипт, и кидаете файл который хотите загрузить.  
Указываете все переменные: локальный файл, тип storage, accessid и секрет, бакет.  
Затем в консоли: sh put_s3_obj.sh   

### PS
Любой ваш лишний пробел добавленный в переменную (canonicalRequest и не только) в запросе, изменят ваш хэш и вы будете получать ошибку `<Code>SignatureDoesNotMatch</Code>`

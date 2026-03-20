# Статья с хабра: 
(https://habr.com/ru/articles/652479/)

```
location @error {
   # задаём дефолтный тип ответа
   default_type text/html;
   # включаем обработку команд SSI
   ssi on;
   # возвращаем шаблон страницы об ошибке
   return 200 "<!DOCTYPE html><html><head><title>$status $status_text</title></head><body><center><h1>$status $status_text</h1></center><hr></body></html>";
}
```

```
# определяем, какие страницы об ошибках будем шаблонизировать
error_page 400 401 402 403 404 405 406 407 408 409 410 411 412 413 414 415 416 417 418 421 422 423 424 425 426 428 429 431 451 500 501 502 503 504 505 506 507 508 510 511 @error;
# а также указываем наследовать страницы об ошибках
error_page_inherit on;
```

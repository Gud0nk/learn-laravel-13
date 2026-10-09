## Установка Laravel (пустой проект)

Обновление пакетного менеджера Composer до последней версии
```php
composer self-update
```

Скачивание и установка чистого проекта laravel в текущую директорию
```php
composer create-project laravel/laravel . 
```

Настройка приложения для работы в качестве API, установка Laravel Sanctum для аутентификации
```php
php artisan install:api
```

Публикация файла конфигурации для настройки CORS-политики(разрешение cross-origin запросов к вашему API c других доменов/фронтенда) 
```php
php artisan config:publish cors
```

Создание символической ссылки из публичной папки **public/storage** в закрытую папку **storage/app/public**.
Это необходимо, чтобы загруженные файлы были доступны по прямой ссылке из браузера. 
```php
php artisan storage:link
```

Создание файла **.htaccess** в корне проекта, чтобы перенаправить все запросы в папку **public**
```php
RewriteEngine on                // включает модуль mod_rewrite в веб-сервере Apache
RewriteRule ^(.*)$ public/$1 [L]   // правило, которое берет абсолютно любой запрошенный url и незаметно для пользователя перенаправляет в папку public
```

## Установка проекта из репозитория
Открой консоль домашней директории сайтов.
Выполните клонирование репозитория и скачайте недостающиеся зависимости
```bash
git clone https://github.com/Gud0nk/learn-laravel-13.git
composer install
```

Скопируем файл **.env** из файла **.env.example**
```bash
copy .env.example .env
```

Сгенерируем ключ шифрования
```bash
php artisan key:generate
```

Выполните миграцию

```bash
php artisan migrate --seed
```

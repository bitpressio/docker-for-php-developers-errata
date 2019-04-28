# Docker for PHP Developers Video Course Errata

Reported errata from the [Docker for PHP Developers](https://bitpress.io/docker-for-php-developers/) video screencasts.

# 06 - Laravel - Setting up MySQL

Unless you know to adjust the `DB_HOST` ENV value to `mysql`, you will get a "Connection Refused" error when you try to run `php artisan db:migrate`. I never mention that the `.env` file should have the following database connection values in order to connect to the MySQL container:

```env
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=homestead
DB_USERNAME=homestead
DB_PASSWORD=secret
```

Specifically the `DB_HOST` value should match the `docker-compose.yml` key for the mysql service and the value should be `DB_HOST=mysql`.

# Esto es una referencia a lo que eh visto en mi trabajo en servidores
# Sistema: Debian 09

En este momento me eh encontrado con un problema de entornos con Laravel 5.2
Como veran el siguiente log 

´
PHP Fatal error:  Uncaught ReflectionException: Class log does not exist in //vendor/laravel/framework/src/Illuminate/Container/Container.php:734
Stack trace:
#0 //vendor/laravel/framework/src/Illuminate/Container/Container.php(734): ReflectionClass->__construct('log')
#1 //vendor/laravel/framework/src/Illuminate/Container/Container.php(629): Illuminate\Container\Container->build('log', Array)
#2 //vendor/laravel/framework/src/Illuminate/Foundation/Application.php(697): Illuminate\Container\Container->make('log', Array)
#3 //vendor/laravel/framework/src/Illuminate/Container/Container.php(849): Illuminate\Foundation\Application->make('log')
#4 //vendor/laravel/framewor in //vendor/laravel/framework/src/Illuminate/Container/Container.php on line 734
´
Esto ha aparecido en la ejecución del mismo y se ha presentado otro problema:

´
E: Failed to fetch https://packages.sury.org/php/pool/main/p/php7.2/php7.2-mysql_7.2.16-1+0~20190307202415.17+stretch~1.gbpa7be82_amd64.deb  404  Not Found
E: Failed to fetch https://packages.sury.org/php/pool/main/p/php7.2/php7.2-opcache_7.2.16-1+0~20190307202415.17+stretch~1.gbpa7be82_amd64.deb  404  Not Found
E: Failed to fetch https://packages.sury.org/php/pool/main/p/php7.2/php7.2-json_7.2.16-1+0~20190307202415.17+stretch~1.gbpa7be82_amd64.deb  404  Not Found
E: Failed to fetch https://packages.sury.org/php/pool/main/p/php7.2/php7.2-readline_7.2.16-1+0~20190307202415.17+stretch~1.gbpa7be82_amd64.deb  404  Not Found
E: Failed to fetch https://packages.sury.org/php/pool/main/p/php7.2/php7.2-mbstring_7.2.16-1+0~20190307202415.17+stretch~1.gbpa7be82_amd64.deb  404  Not Found
E: Failed to fetch https://packages.sury.org/php/pool/main/p/php7.2/php7.2-curl_7.2.16-1+0~20190307202415.17+stretch~1.gbpa7be82_amd64.deb  404  Not Found
E: Failed to fetch https://packages.sury.org/php/pool/main/p/php7.2/php7.2-zip_7.2.16-1+0~20190307202415.17+stretch~1.gbpa7be82_amd64.deb  404  Not Found
E: Failed to fetch https://packages.sury.org/php/pool/main/p/php7.2/php7.2-fpm_7.2.16-1+0~20190307202415.17+stretch~1.gbpa7be82_amd64.deb  404  Not Found
E: Failed to fetch https://packages.sury.org/php/pool/main/p/php7.2/php7.2-xml_7.2.16-1+0~20190307202415.17+stretch~1.gbpa7be82_amd64.deb  404  Not Found
E: Failed to fetch https://packages.sury.org/php/pool/main/p/php7.2/php7.2-cli_7.2.16-1+0~20190307202415.17+stretch~1.gbpa7be82_amd64.deb  404  Not Found
E: Failed to fetch https://packages.sury.org/php/pool/main/p/php7.2/php7.2-common_7.2.16-1+0~20190307202415.17+stretch~1.gbpa7be82_amd64.deb  404  Not Found
E: Failed to fetch https://packages.sury.org/php/pool/main/p/php7.2/libapache2-mod-php7.2_7.2.16-1+0~20190307202415.17+stretch~1.gbpa7be82_amd64.deb  404  Not Found
E: Failed to fetch https://packages.sury.org/php/pool/main/p/php7.2/php7.2_7.2.16-1+0~20190307202415.17+stretch~1.gbpa7be82_all.deb  404  Not Found
E: Failed to fetch https://packages.sury.org/php/pool/main/p/php7.2/php7.2-gd_7.2.16-1+0~20190307202415.17+stretch~1.gbpa7be82_amd64.deb  404  Not Found
´
pues este problema aplicando el siguiente comando se puede resolver:
´
sudo wget -O /etc/apt/trusted.gpg.d/php.gpg https://packages.sury.org/php/apt.gpg
´

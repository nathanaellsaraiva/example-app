<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>


### INSTALANDO DEPENDENCIAS

```sh
sudo apt update

sudo apt install git
sudo apt install nginx
sudo apt install mysql-server
sudo apt install curl 

sudo apt install php8.1 
sudo apt install php8.1-ctype php8.1-curl php8.1-dom php8.1-fileinfo php8.1-mbstring php8.1-opcache php8.1-pdo php8.1-tokenizer php8.1-xml php8.1-zip php8.1-fpm php8.1-mysql
sudo apt install unzip p7zip


curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash 
source ~/.bashrc  
nvm install node

sudo systemctl enable mysql
sudo systemctl enable nginx
sudo systemctl enable php8.1-fpm

sudo systemctl status mysql
sudo systemctl status nginx
sudo systemctl status php8.1-fpm
```

### CONFIGURANDO MYSQL
```sh
sudo mysql
# Comando: ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password by '123456789';
# Comando: exit;
```
```sh
sudo mysql_secure_installation
# Siga os passos da instalação
```

```sh
sudo mysql -u root -p
# Comando: create database example;
# Comando: exit;
```

### INSTALANDO COMPOSER
```sh
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === '55ce33d7678c5a611085589f1f3ddf8b3c52d662cd01d4ba75c0ee0459970c2200a51f492d557530c71c15d8dba01eae') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
sudo mv composer.phar /usr/local/bin/composer
composer --version
```

### CLONE DO REPOSITORY
```sh
sudo chmod  o+w /var/www
cd /var/www/
git clone https://github.com/nathanaellsaraiva/example-app.git
cd example-app/
cp .env.example .env
nano .env
# Altere o name e ajuste as conexões
```

### CONFIGURANDO O PROJETO
```sh
composer install --optimize-autoloader --no-dev
sudo chmod -R 777 storage
sudo chmod -R 777 bootstrap
php artisan migrate
php artisan key:generate

npm install
npm run build
```


### CONFIGURANDO NGINX
```sh
sudo lsof -i :80 # UTILIZE PARA VER SERVIÇOS RODANDO NA PORTA 
sudo mv /etc/nginx/sites-available/default ~/
sudo nano /etc/nginx/sites-available/default
sudo nginx -t # UTILIZE PARA VER SE AS CONFIGURAÇÕES DE SITES DO NGINX ESTÃO CORRETAS
sudo systemctl restart nginx
```




How to setup existing Magento 2 Project?

Follow below steps to setup existing magento 2 project.

## 1. Import Database :

Import the database by using this command. mysql -u [username] -p newdatabase < [database name].sql;

## 2. Clone/Extract the Source code.

Clone or extract the source code of magento 2.

## 3. Run Composer Install Or Composer Update Command :

Run the composer update command, If composer is not installed then run first composer install & then composer update command. (If you get any memory limit error then run COMPOSER_MEMORY_LIMIT=-1 composer update command.)

## 4. Create env.php file : Run this command to create env.php file.

php bin/magento setup:config:set --db-user="dbusername" --db-password="dbpassword" --db-name="dbname" or add any existing env.php file and update the host, dbname, username & password.

## 5. Create config.php file : Run this command to create config.php file.

php bin/magento module:enable --all

## 6. Run the following commands one by one :

php bin/magento setup:upgrade

php bin/magento setup:di:compile

php bin/magento setup:di:compile

## 7. Change the base url in database :

Table name : core_config_data

path : web/unsecure/base_url
path : web/secure/base_url

Or you can change by using below commands.

php bin/magento setup:store-config:set --base-url="http://127.0.0.1/magento/"

php bin/magento setup:store-config:set --base-url="http://127.0.0.1/magento/"


Ex: http://127.0.0.1/magento/

## 8. Clean and Flush the cache :

php bin/magento cache:clean and php bin/magento cache:flush.


## 9. Now open url in browser.

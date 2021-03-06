<a href="http://www.ecomdev.org/services/magento-development?utm_source=github&utm_medium=logo&utm_campaign=github">![EcomDev](http://www.ecomdev.org/wp-content/themes/ecomdev/images/logo.png)</a>

Magento PHPUnit Integration
===========================

Magento is a quite complex platform without built in unit test suite, so the code is not oriented on running tests over it.

This extension was created especially for resolving this problem and promoting test driven development practices in Magento developers community. It doesn't change core files or brake your Magento instalment database, because all the system objects are replaced during the run-time with the test ones and a separate database connection is used for tests.

System Requirements
-------------------
* PHP 7.2 or higher
* PHPUnit 8.x
* Magento CE 1.9.2.4

Build Status
------------
* Latest Release: [![Master Branch](https://travis-ci.org/EcomDev/EcomDev_PHPUnit.png?branch=master)](https://travis-ci.org/EcomDev/EcomDev_PHPUnit)
* Development Branch: [![Development Branch](https://travis-ci.org/EcomDev/EcomDev_PHPUnit.png?branch=dev)](https://travis-ci.org/EcomDev/EcomDev_PHPUnit)


Documentation
-------------

* [EcomDev_PHPUnit version 0.2.0](http://www.ecomdev.org/wp-content/uploads/2011/05/EcomDev_PHPUnit-0.2.0-Manual.pdf)

Also you may follow our related [blogposts](http://www.ecomdev.org/tag/phpunit).

Installation
------------


1. There are two ways of obtaining the extension:    
    * Use [Module Manager](https://github.com/colinmollenhour/modman) 
        
     ```bash
     modman clone git://github.com/EcomDev/EcomDev_PHPUnit.git 
     ```
    * Add extension as dependency in your composer.json to install it from [Magento Composer Repository](http://packages.firegento.com/)
      ```json
      {
            "require": {
               "ecomdev/ecomdev_phpunit": "*"
            }
      }
      ```

2. Open your terminal and navigate to your magento directory for performing the following command, they are required to configure system for running the test suite 
    ```bash
    # Shell scripts needs to be run from this directory
    cd $YOUR_MAGENTO_DIRECTORY/shell 
    # Specify your test database name and base url for controller tests
    php ecomdev-phpunit.php -a magento-config --db-name $DB_NAME --base-url http://your.magento.url/
    ```
    If you receive a warning on PHPUnit checks for optional packages, run the following command
    ```bash
    php ecomdev-phpunit.php -a fix-autoloader
    ```

3. Run the unit tests first time for installing test database. It will take about 3 minutes.

        $ phpunit 

4. If it shows that there was no tests found, it means that extension was successfully installed. If it shows some errors, then it means, that your customizations has install scripts that relay on your current database data and you should fix them. Or use your dev database as a base for the tests, but prior first time running the suite.


Issue Tracker
-------------
We use github issue tracker only for contributions management. If you want to post an issue please use our [Issue Tracker](http://project.ecomdev.org/projects/mage-unit)

Contributions
-------------

If you want to take a part in improving our extension please create branches based on dev one. 

###Create your contribution branch: 
   
	$ git checkout -b [your-name]/[feature] dev


Then submit them for pull request. 


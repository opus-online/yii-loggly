# Yii Loggly

This module is a log writer for [Yii](http://www.yiiframework.com/) that will send all log messages to a [Loggly](http://loggly.com/) input.

### Requirements

 - php >= 5.2
 - php5-curl extension
 - Yii 1.1.13 (should work on prior versions but not tested)

### Usage

Install using composer ( https://packagist.org/packages/opus-online/yii-loggly )

At the head of protected/config/main.php add:

Yii::setPathOfAlias('OpusOnline.Loggly', dirname(__FILE__) . '/../vendors/opus-online/yii-loggly');

In the components section add:

```php
    'log' => array(
        'class' => 'CLogRouter',
        'routes' => array(
            array(
                'class'=> '\OpusOnline\Loggly\Route',
                'inputKey' => '<KEY>',
                'finishRequest' => true,
                'levels'=> 'error, warning, info',
                'tag' => 'staging,php'
            ),
        ),
    ),
```
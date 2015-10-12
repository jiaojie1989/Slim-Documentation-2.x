# 系统需求

* PHP版本 >= 5.3.0
* mcrypt扩展（*仅当*使用加密cookies时）

# 安装

## 通过Composer

在项目中安装composer

    curl -s https://getcomposer.org/installer | php

在项目根目录下建立一个`composer.json`文件:

    {
        "require": {
            "slim/slim": "2.*"
        }
    }

通过composer安装:

    php composer.phar install

向你的应用中的`index.php`文件增加以下代码:

    <?php
    require 'vendor/autoload.php';

## 常规安装

下载并将Slim框架解压到项目目录，并在应用的`index.php`文件中添加`require`。
同时需要调用注册Slim的自动加载。

    <?php
    require 'Slim/Slim.php';
    \Slim\Slim::registerAutoloader();

# Hello World

获取Slim应用实例:

    $app = new \Slim\Slim();

定义HTTP GET路由:

    $app->get('/hello/:name', function ($name) {
        echo "Hello, $name";
    });

运行Slim应用:

    $app->run();

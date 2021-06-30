# 开启服务与关闭服务

因为我的PHP是用brew安装的，安装的时候还选择了@7.4，所以命令也要与众不同；



# Mac如何重启php-fpm、开启、关闭php-fpm

```
brew services start php@7.4 //开启
brew services restart php@7.4 //重启[未验证]
brew services stop php@7.4 //关闭[未验证]
```



>  具体链接https://viencoding.com/article/142



# 正常情况

 关闭php-fpm

```
sudo  killall  php-fpm
```

 启动php-fpm

```
sudo  php-fpm
```

 重启php-fpm

先关闭php-fpm、再自动php-fpm即可

```
sudo  killall  php-fpm
sudo  php-fpm
```
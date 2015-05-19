# nginx用于开发环境
一次学习，稳定可靠的nginx服务，值得拥有

## why
* 运行稳定可靠
* 功能丰富，提供必要的静态服务和请求转发
* nginx的学习和使用属于可沉淀技能

## how to
* 静态服务
```
root /home/{username}/webroot;
cation ~* (/|.html|.appcache)$ {
    expires 0;
}
location ~* \.(js|css|png|jpg|jpeg|gif|ico|webp)$ {
    expires 0;
}
```

* 请求转发
```
location /api/ {
    proxy_pass http://your.app.com/api/;
}
````

* 映射开发目录至webroot
```
mkdir -p ~/webroot
cd ~/webroot
ln -s ~/your-project project
```

* 开发环境DNS解析(可选)
```
resolver 192.168.1.251;
```


-- Inspired by 程老师

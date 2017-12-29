# 帮助
    nginx -h
# 启动
    start niginx
    打开任务管理器，单靠两个nginx.exe，说明已经启动了
    访问：http://127.0.0.1 Welcome to nginx!
# 核心配置文件
    nginx.conf

# 检查配置文件
    nginx -t

# 重新加载配置文件
    nginx -s reload

# 关闭
    nginx -s stop

# 样例

## demo1
    server_name 172.16.9.86:32854;
    location / {
        proxy_pass http://172.16.9.86:32854;
    }

## demo2
    location ~ \.jsp$ {  
            proxy_pass http://localhost:8080;  
    }  
          
    location ~ \.(html|js|css|png|gif)$ {  
        root D:/software/developerTools/server/apache-tomcat-7.0.8/webapps/ROOT;  
    }

## demo3
    upstream tosin_test {
        server 172.16.9.235:8080 weight=1;
        server 172.16.9.248:10090 weight=5;
        server 172.16.9.248:10091 weight=5;
    }
    server {
        listen       80;
        #server_name  localhost;
        location / {
            proxy_pass http://tosin_test;
        }

Nginx简介及配置文件详解

http://blog.csdn.net/hzsunshine/article/details/63687054

http://nginx.org/en/docs/http/ngx_http_core_module.html

http://nginx.org/en/docs/http/ngx_http_proxy_module.html

windows Nginx基本使用方法
    http://blog.csdn.net/u011418717/article/details/52776090


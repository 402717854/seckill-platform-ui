# seckill-platform-ui

seckill-platform 前端源码

#### 项目源码

|     |   后端源码  | 前端源码                                             |
|---  |--- |--------------------------------------------------|
|  github   |  https://github.com/402717854/seckill-platform-group   | https://github.com/402717854/seckill-platform-ui |

#### 开发文档
[https://402717854.vip](https://402717854.vip)

#### 体验地址
[https://402717854.vip/demo](https://402717854.vip/demo)

#### 前端模板

初始模板基于： [https://github.com/PanJiaChen/vue-element-admin](https://github.com/PanJiaChen/vue-element-admin)

模板文档： [https://panjiachen.github.io/vue-element-admin-site/zh/guide/](https://panjiachen.github.io/vue-element-admin-site/zh/guide/)

#### Build Setup
``` bash
# 配置镜像加速
https://www.ydyno.com/archives/1219.html

# 安装依赖
npm install

# 启动服务 localhost:8013
npm run dev

# 构建生产环境
npm run build:prod
```

#### nginx配置
     server {
        listen       80;
        server_name  localhost;

        #charset koi8-r;

        #access_log  logs/host.access.log  main;
        #访问前端工程
        location / {
            root   dist;
            #index  index.html index.htm;
            try_files $uri $uri/ /index.html;
        }
        #后端服务反向代理--负载均衡做准备
        location /gateway {
          proxy  http://192.168.66.16:8201
          root   html;
          index  index.html index.htm;
        }

        #error_page  404              /404.html;

        # redirect server error pages to the static page /50x.html
        #
        error_page   500 502 503 504  /50x.html;
        location = /50x.html {
            root   html;
        }
     }


     
     nginx常用命令
     ./nginx -t        -- 验证nginx配置文件是否正确
     ./nginx  --启动

    ./nginx -s stop --关闭
    
    ./nginx -s reload --重启
     
#### 常见问题

1、linux 系统在安装依赖的时候会出现 node-sass 无法安装的问题

解决方案：
```
1. 单独安装：npm install --unsafe-perm node-sass 
2. 直接使用：npm install --unsafe-perm
```

2、加速node-sass安装

https://www.ydyno.com/archives/1219.html

#### 特别鸣谢

- 感谢 [JetBrains](https://www.jetbrains.com/) 提供的非商业开源软件开发授权

- 感谢 [PanJiaChen](https://github.com/PanJiaChen/vue-element-admin) 大佬提供的前端模板

- 感谢 [Moxun](https://github.com/moxun1639) 大佬提供的前端 Crud 通用组件

- 感谢 [zhy6599](https://gitee.com/zhy6599) 大佬提供的后端运维管理相关功能

- 感谢 [j.yao.SUSE](https://github.com/everhopingandwaiting) 大佬提供的匿名接口与Redis限流等功能

- 感谢 [d15801543974](https://github.com/d15801543974) 大佬提供的基于注解的通用查询方式
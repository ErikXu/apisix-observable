# 使用 Docker Compose 启动 Apisix

参考：<https://github.com/apache/apisix-docker>

## 修改 apisix 配置

按照以下提示修改 `apisix_conf/config.yaml`

``` yaml
...
    admin_key:
      - name: "admin"
        key: {admin-key}            # admin key，用于调用管理接口，示例：edd1c9f034335f136f87ad84b625c8f1
        role: admin                 

      - name: "viewer"
        key: {viewer-key}           # viewer key，示例：4054f7cf07e344346cd3f287985e76a2
        role: viewer
...
```

## 修改 dashboard 配置

按照以下提示修改 `dashboard_conf/conf.yaml`

``` yaml
...

  users:               
    - username: admin  
      password: {admin-password}     # admin password
    - username: user
      password: {user-password}      # user password

...
```

## 启动 Apisix

``` bash
docker compose -p docker-apisix up -d
```
## 移除 Apisix

``` bash
docker compose -p docker-apisix down
```

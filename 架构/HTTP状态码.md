## HTTP状态码

- 1** 信息状态码
  - 100 继续
  - 101 切换协议

- 2** 成功状态码
  - **200 OK 请求成功**
  - 201 已创建
  - 202 已接受
  - 203 非授权信息
  - 204 无内容
  - 205 重置内容
  - 206 部分内容

- 3** 重定向
  - 300 多种选择
  - **301 Moved Permanently 永久重定向**
  - **302 Found 临时重定向**
  - 303 查看其它地址
  - **304 Not Modified 未修改**
  - 305 使用代理

- 4** 客户端错误
  - **400 Bad Request 请求的语法错误**
  - 401 Unauthorized 要求身份验证
  - **403 Forbidden 服务器拒绝执行该请求**
  - **404 Not Found 未找到资源**

- 5** 服务器错误
  - **500 Internal Server Error 服务器内部错误**
  - 501 服务器不支持该功能，无法完成请求
  - **502 Bad Gateway 服务器作为网关服务器执行请求时，从远程服务器接收到了无效的响应**
  - 503 Service Unavailable 系统维护
  - 504 Gateway Time-out 超时
  - 505 HTTP Version not supported 服务器不支持请求的HTTP协议版本
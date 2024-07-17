HTTP协议定义了多种请求方法，用于指定客户端希望对服务器上的资源执行的操作。常用的HTTP请求方法包括以下几种：

### 1. GET

**作用**：请求指定的资源。请求使用GET方法时，应该只请求数据，而不应有任何副作用（比如修改数据）。

**示例**：获取主页内容
```
GET /index.html HTTP/1.1
Host: www.example.com
```

### 2. POST

**作用**：向指定的资源提交数据进行处理（例如提交表单或上传文件）。数据包含在请求体中。POST方法可能会导致资源的状态或服务器上的数据发生变化。

**示例**：提交登录表单
```
POST /login HTTP/1.1
Host: www.example.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 27

username=user&password=pass
```

### 3. PUT

**作用**：向指定资源上传其最新内容。如果资源不存在，服务器可以创建该资源。

**示例**：上传或更新文件
```
PUT /upload/file.txt HTTP/1.1
Host: www.example.com
Content-Type: text/plain
Content-Length: 20

This is file content.
```

### 4. DELETE

**作用**：删除指定的资源。

**示例**：删除文件
```
DELETE /file.txt HTTP/1.1
Host: www.example.com
```

### 5. HEAD

**作用**：与GET方法一样，请求指定的资源，但不返回资源的主体部分。用于获取报头信息。

**示例**：获取资源的元数据
```
HEAD /index.html HTTP/1.1
Host: www.example.com
```

### 6. OPTIONS

**作用**：用于描述目标资源的通信选项。客户端可以向服务器发送OPTIONS请求，以了解服务器支持的HTTP方法。

**示例**：获取服务器支持的HTTP方法
```
OPTIONS /index.html HTTP/1.1
Host: www.example.com
```

### 7. PATCH

**作用**：用于对资源进行部分修改。PATCH方法在请求体中包含要修改的内容，而不是整个资源的内容。

**示例**：部分更新文件内容
```
PATCH /file.txt HTTP/1.1
Host: www.example.com
Content-Type: application/json
Content-Length: 25

{
    "field": "new value"
}
```

### 8. TRACE

**作用**：回显服务器收到的请求，用于测试或诊断。

**示例**：回显请求
```
TRACE /index.html HTTP/1.1
Host: www.example.com
```

### 9. CONNECT

**作用**：用于建立一个到达目的服务器的隧道，多用于代理服务器（例如用于HTTPS通过HTTP代理）。

**示例**：建立隧道
```
CONNECT www.example.com:443 HTTP/1.1
Host: www.example.com
```

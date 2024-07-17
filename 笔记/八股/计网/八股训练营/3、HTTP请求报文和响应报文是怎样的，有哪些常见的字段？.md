## HTTP请求报文

一个HTTP请求报文通常包含以下部分：

1. **请求行（Request Line）**：包括[[统一资源标识符|[4、HTTP有哪些请求方式？|请求方式]]和HTTP版本。
2. **请求头部（Request Headers）**：包含客户端向服务器发送的附加信息，以键值对的形式存在。
```ad-info
请求头的字段较多，常使用的包含以下几个：

- Host：请求的服务器的域名。
- Accept：客户端能够处理的媒体类型。
- Accept-Encoding：客户端能够解码的内容编码。
- Authorization：用于认证的凭证信息，比如token数据。
- Content-Length：请求体的长度。
- Content-Type：请求体的媒体类型。
- Cookie：存储在客户端的cookie数据。
- If-None-Match：资源的ETag值，用于缓存控制。
- Connection：管理连接的选项，如 keep-alive。
```
3. **空行**：用于分隔头部和主体。
4. **请求主体（Request Body）**：包含要发送给服务器的[^2]数据（可选）。
```ad-tip
通常用于 `POST` 和 `PUT` 请求
```

![[Pasted image 20240709174542.png]]

**示例：GET请求**

```Bash
GET /index.html HTTP/1.1
Host: www.example.com
```

**示例：POST请求**

```
POST /login HTTP/1.1
Host: www.example.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 27

username=user&password=pass
```

---
## HTTP响应报文

一个HTTP响应报文通常包含以下部分：

1. **状态行（Status Line）**：包括HTTP版本、状态码和状态描述。
2. **响应头部（Response Headers）**：包含服务器返回给客户端的附加信息，以键值对的形式存在。
```ad-info
- Content-Type：指定响应主体的媒体类型。
    
- Content-Length：指定响应主体的长度（字节数）。
    
- Server：指定服务器的信息。
    
- **Expires**: 响应的过期时间，之后内容被认为是过时的。
    
- **ETag**: 响应体的实体标签，用于缓存和条件请求。
    
- **Last-Modified**： 资源最后被修改的日期和时间。
    
- Location：在重定向时指定新的资源位置。
    
- Set-Cookie：在响应中设置Cookie。
    
- Access-Control-Allow-Origin: 跨源资源共享（CORS）策略，指示哪些域可以访问资源。
```
3. **空行**：用于分隔头部和主体。
4. **响应主体（Response Body）**：包含服务器返回的数据。

**示例：成功的响应（200 OK）**

```
HTTP/1.1 200 OK                      (状态行)
Date: Mon, 12 Jul 2021 19:45:00 GMT  (响应头部)
Server: Apache/2.4.41 (Ubuntu)
Last-Modified: Mon, 12 Jul 2021 19:30:00 GMT
Content-Length: 137
Content-Type: text/html
                                      (空行)
<!DOCTYPE html>                       (响应主体)
<html>
<head>
    <title>Example</title>
</head>
<body>
    <h1>Welcome to Example.com!</h1>
</body>
</html>
```

---


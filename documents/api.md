# hwfc API

- [域名及ip地址](#域名及ip地址)
    - [域名](#域名)（待备案）
    - [ip地址](#ip地址)（待实名认证）
- [返回状态说明](#返回状态说明)
    - [通用类状态码](#通用类状态码)（developing）
- [主页](#主页)
    - [获取轮播热图](#获取轮播热图)（developing）
    - [获取最新预告内容](#获取最新预告内容)（developing）
    - [获取最新文章内容](#获取最新文章内容)（developing）
    - [获取热点视频](#获取热点视频)（developing）

<a name="域名及ip地址"></a>
## 域名及ip地址

<a name="域名"></a>
### 域名（待备案）
helloworldfc.com

<a name="ip地址"></a>
### ip地址（待实名认证）
119.29.171.241

<a name="返回状态说明"></a>
## 返回状态说明

<a name="通用类状态码"></a>
### 通用类状态码（developing）

| Code | Description |
|------|-------------|
|200|请求成功|
|404|请求的资源不存在|
|500|服务器内部错误|

<a name="主页"></a>
## 主页

<a name="获取轮播热图"></a>
### 获取轮播热图（developing）

Request URI:

```
GET /someurl
```

Response Properties:

| Property | Description | Type |
|----------|-------------|------|
|url|四张热图的链接数组|string array|

Response Example:

```json
{
    "url": ["someurl", "someurl", "someurl", "someurl"]
}
```

<a name="获取最新预告内容"></a>
### 获取最新预告内容（developing）

Request URI:

```
GET /someurl
```

Response Properties:

| Property | Description | Type |
|----------|-------------|------|
|time|预告的 时间|string|
|content|预告的 内容|string|

Response Example:

```json
{
    "time": "格式待定的时间",
    "content": "贝岗聚餐"
}
```

<a name="获取最新文章内容"></a>
### 获取最新文章内容（developing）

Request URI:

```
GET /someurl
```

Response Properties:

| Property | Description | Type |
|----------|-------------|------|
|title|文章的 标题|string|
|upload_time|文章的 上传时间|string|
|author|文章的 作者|string|
|brief|文章的 摘要|string|

Response Example:

```json
{
    "title": "如何干一名优秀的程序员",
    "upload_time": "2017-05-01",
    "author": "liveipool",
    "brief": "字数待定的摘要"
}
```

<a name="获取热点视频"></a>
### 获取热点视频（developing）

Request URI:

```
GET /someurl
```

Response Properties:

| Property | Description | Type |
|----------|-------------|------|
|url|两个热点视频的链接数组|string array|

Response Example:

```json
{
    "url": ["someurl", "someurl"]
}
```

# hwfc API

- [域名及ip地址](#域名及ip地址)
  - [域名](#域名)（待备案）
  - [ip地址](#ip地址)（待实名认证）
- [返回对象说明](#返回对象说明)
  - [通用类状态码](#通用类状态码)（developing）
  - [成功返回](#成功返回)
  - 错误处理（developing）
- [Models](#Models)
  - [Essay](#Essay)
    - [获取所有文章](#获取所有文章)
    - [获取最新文章](#获取最新文章)
    - [上传新文章](#上传新文章)

<a name="域名及ip地址"></a>

## 域名及ip地址

<a name="域名"></a>

### 域名（待备案）

helloworldfc.com

<a name="ip地址"></a>

### ip地址（待实名认证）

119.29.171.241

<a name="返回对象说明"></a>

## 返回对象说明

<a name="通用类状态码"></a>

### 通用类状态码（developing）

| Code | Description |
|------|-------------|
|200|请求成功|
|404|请求的资源不存在|
|500|服务器内部错误|

<a name="成功返回"></a>

### 成功返回

当成功返回时，内容将会被包裹在`data`中。

```javascript
{
    data: {
        // ...
    }
}
```

<a name="错误处理"></a>

### 错误处理

编写中……

<a name="Models"></a>

## Models

<a name="Essay"></a>

### Essay

| Property | Description | Type |
|----------|-------------|------|
|title|文章的标题|string|
|uploadTime|文章的上传时间|string|
|author|文章的作者|string|
|brief|文章的摘要|string|

<a name="获取所有文章"></a>

#### 获取所有文章

Request URI:

```http
GET /api/essays/
```

Response Example:

```json
{
  "data": [
    {
      "_id": "59182ccee6c77a6cc88f9f55",
      "title": "如何干一名优秀的程序员",
      "author": "liveipool",
      "brief": "字数待定的摘要",
      "uploadTime": "2017-05-14T10:09:18.907Z",
      "__v": 0
    },
    {
      "_id": "59182d3be6c77a6cc88f9f56",
      "title": "如何干一名优秀的程序员2",
      "author": "liveipool2",
      "brief": "字数待定的摘要2",
      "uploadTime": "2017-05-14T10:11:07.310Z",
      "__v": 0
    }
  ]
}
```

<a name="获取最新文章"></a>

#### 获取最新文章

Request URI:

```http
GET /api/essays/hot
```

Response Example:

```json
{
  "data": {
    "_id": "59182f015612b65c44664af0",
    "title": "123123",
    "author": "222",
    "brief": "12312321",
    "uploadTime": "2017-05-14T10:18:41.722Z",
    "__v": 0
  }
}
```

<a name="上传新文章"></a>

#### 上传新文章

> 提交时不需要提供`uploadTime`字段，后端会自动生成。

Request URI:

```http
POST /api/essays/
```

Request body:

```json
{
    "title": "这是一个标题",
    "author": "我是作者",
    "brief": "文章的简单介绍"
}
```

Response Example:

```json
{
  "data": {
    "__v": 0,
    "title": "这是一个标题",
    "author": "我是作者",
    "brief": "文章的简单介绍",
    "uploadTime": "2017-05-14T12:25:41.824Z",
    "_id": "59184cc55d2d2a42f83d9524"
  }
}
```

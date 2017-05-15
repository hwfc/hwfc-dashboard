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
    - [获取特定文章](#获取特定文章)
    - [新建文章](#新建文章)

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

```json
{
    "data": {
    }
}
```

<a name="错误处理"></a>

### 错误处理

通常情况下，会返回这样的错误信息：

```json
{
    "status": "error",
    "cause": "错误名称",
    "message": "错误信息"
}
```

偶尔会返回这样的错误信息：

```json
{
    "err": "错误信息"
}
```

<a name="Models"></a>

## Models

<a name="Essay"></a>

### Essay

| Property | Description | Type |
|----------|-------------|------|
|title|文章的标题|string|
|uploadTime|文章的上传时间|string|
|author|文章的作者|string|
|content|文章的内容|string|

<a name="获取所有文章"></a>

#### 获取所有文章

> 不带`content`字段，带有`brief`字段。

Request URI:

```http
GET /api/essays/
```

Response Example:

```json
{
  "data": [
    {
      "uploadTime": "2017-05-14T17:46:30.092Z",
      "title": "为什么我这么机智",
      "author": "小方",
      "brief": "1234567890",
      "id": "591897f61f648b1b6ca28354"
    },
    {
      "uploadTime": "2017-05-14T18:21:53.724Z",
      "title": "你好呀",
      "author": "hhk",
      "brief": "666",
      "id": "5918a04168088e32d8b526ab"
    }
  ]
}
```

<a name="获取最新文章"></a>

#### 获取最新文章

> 不带`content`字段，带有`brief`字段。

Request URI:

```http
GET /api/essays/hot
```

Response Example:

```json
{
  "data": {
    "uploadTime": "2017-05-14T18:21:53.724Z",
    "title": "你好呀",
    "author": "hhk",
    "brief": "666",
    "id": "5918a04168088e32d8b526ab"
  }
}
```

<a name="获取特定文章"></a>

#### 获取特定文章

> 带有`content`字段，不带`brief`字段。

Request URI:

```http
GET /api/essays/:id
```

Response Example:

```json
{
  "data": {
    "uploadTime": "2017-05-15T04:21:01.366Z",
    "title": "这是一个标题",
    "author": "我是作者",
    "content": "文章的内容",
    "id": "59192cad32750f6814ee98cf"
  }
}
```

<a name="新建文章"></a>

#### 新建文章

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
    "content": "文章的内容"
}
```

Response Example:

```json
{
  "data": {
    "uploadTime": "2017-05-15T04:21:01.366Z",
    "title": "这是一个标题",
    "author": "我是作者",
    "content": "文章的内容",
    "id": "59192cad32750f6814ee98cf"
  }
}
```

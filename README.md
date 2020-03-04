在仓库根目录创建 xxx.json文件为仓库入口(名称自定义)
```json

{
    "type": "MyACG搜索源",
    "name": "",
    "summary": "",
    "sources": "",
    "versionName": "",
    "versionCode": 1,
    "list": [
        {
            "name": "",
            "url": "",
            "checked": true,
            "category": 1
        }
    ]
}

```
| 属性        | 类型           | 必填 | 注释                                        |
| ----------- | -------------- | ---- | ------------------------------------------- |
| name        | String(文本型) | 是   | 搜索源仓库名称                              |
| summary     | String(文本型) | 是   | 搜索源仓库介绍                              |
| sources     | String(文本型) | 是   | 搜索源目录链接                              |
| versionName | String(文本型) | 是   | 搜索源仓库版本名称                          |
| versionCode | int(整数型)    | 是   | 搜索源仓库代码版本 (-2147483648~2147483647) |
|             |                |      |                                             |
| list        | null           | 是     |  搜索源列表                              |
| name        | String(文本型) | 是     | 搜索源名称                                  |
| url         | String(文本型) | 是     | 搜索源介绍                                   |
| checked     | bool(逻辑型)   | 是     | 搜索源默认开关                                   |
| category    | int(整数型)    | 是     | 搜索源类型1:链接2:漫画解析3:视频解析4:小说解析 |


在仓库的搜索源目录创建 xxx.json文件(名称建议以网站名称为题)
```json

{
  "name": "",
  "charset": "",
  "dependencies":"",
  "request": "",
  "metadata": {
    "list": "",
    "name": "",
    "author": "",
    "img": "",
    "link": ""
  },
  "detail": {
    "author": "",
    "summary": "",
    "upDate": "",
    "catalog_link": "",
    "tab": {
      "list": "",
      "name": ""
    },
    "catalog": {
      "list": "",
      "chapter": {
        "list": "",
        "name": "",
        "link": "",
        "orderBy": 1,
        "category": 1
      }
    }
  },
  "content": {
    "list": "",
    "link": "",
    "link2": "",
    "text": "",
    "mode": 1
  }
}

```
| 属性         | 类型                      | 必填 | 注释                         |
| ------------ | ------------------------- | ---- | ---------------------------- |
| name         | String(文本型)            | 是   | 搜索源名称                   |
| charset      | String(文本型)            | 是   | 源网站编码类型               |
| dependencies | String(文本型)            | 否   | js依赖库文件链接[一般不使用] |
| request      | String(文本型)            | 是   | 搜索请求链接                 |
|              |                           |      |                              |
| metadata     | null                      | 是   | 搜索结果处理                 |
| list         | javaScript代码,返回为数组 | 是   | 搜索结果列表                 |
| name         | javaScript代码,返回为文本 | 是   | 搜索结果名称                 |
| author       | javaScript代码,返回为文本 | 是   | 搜索结果作者                 |
| img          | javaScript代码,返回为文本 | 是   | 搜索结果缩略图               |
| link         | javaScript代码,返回为文本 | 是   | 搜索结果跳转链接             |
|              |                          |     |                            |
| detail       | null                     | 否   | 进入详细界面(不填则进入结果网页) |
| author       | javaScript代码,返回为文本 | 是   | 详细界面的作者信息               |
| summary      | javaScript代码,返回为文本 | 是   | 详细界面的介绍                |
| upDate       | null                      | 是   | 搜索结果处理                 |
| catalog_link | javaScript代码,返回为文本 | 否   | 目录跳转链接[一般不使用]         |
|              |                           |      |                              |
| tab         | null                       | 否   | 详细界面tab[一般不使用]        |
| list       | javaScript代码,返回为数组    | 是   | tab列表                       |
| name       | javaScript代码,返回为文本    | 是   | tab名称                       |
|              |                           |      |                              |
| catalog      | null                      | 是   | 目录信息                     |
| list         | javaScript代码,返回为数组  | 否   | tab对应目录[一般不使用]       |
|              |                           |      |                              |
| chapter      | null                      | 是   | 集数信息                     |
| list         | javaScript代码,返回为数组  | 否   | 章节(集数)列表                |
| name         | javaScript代码,返回为文本  | 是   | 章节(集数)名称               |
| link         | javaScript代码,返回为文本  | 是   | 章节(集数)跳转链接          |
| orderBy      | javaScript代码,返回为文本  | 是   | 章节(集数)跳转链接          |
| category     | int(整数型)               | 是   | 排列方式 0:顺序1:倒序          |
| category     | int(整数型)               | 是   | 解析方式 1:链接2:漫画解析3:视频解析4:小说解析          |
|              |                           |      |                              |
| content      | null                      |否    |内容 链接:不用填 漫画解析:必填 视频解析:不用填  小说解析:必填 |
| list         | javaScript代码,返回为数组  | 是   | (漫画使用)页数           |
| link         | javaScript代码,返回为文本  | 否   | (漫画使用)图片链接或跳转页面链接       |
| link2        | javaScript代码,返回为文本  | 否   | (漫画使用)图片链接[一般不使用]如果link为跳转页面则使用这条获取跳转页面的图链接|
| text        | javaScript代码,返回为文本  | 否   | (小说使用)文章内容      |
| mode        | int(整数型)               | 是   | 1:横向阅读-左滑 2：横向阅读-右滑       |
jsoup语法:
https://jsoup.org/apidocs/org/jsoup/select/Selector.html

jsonPath语法:
https://github.com/json-path/JsonPath/blob/master/README.md

jsoup调试网站https://try.jsoup.org/

jsonPath调试工具https://github.com/zykzml7788/JsonPathUtil

js语言调用类

```js

jsoups(data,jsoup语句)//返回为数组

jsoup(data,jsoup语句)

jsoup附加语句
@attr->

jsonPaths(data,jsonPath语句)//返回为数组

jsonPath(data,jsonPath语句)

javaScript(data)//执行javaScript(常用执行网页内的javaScript)

getURL(data)//获取当前解析页面链接

pathURL(data)//链接补充路径

pathURL2(data,url)//链接补充路径2

strmiddle(data,左边文本,右边文本)//取文本中间

```

快用这些去抓取你心怡的网站吧,再也不见广告!再也不翻找链接找资源!
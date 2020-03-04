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
| category    | int(整数型)    | 是     | 搜索源类型1:链接2:漫画解析3:视频解析4:小说解析                 |

```json

{
    "name": "搜索源名称",
    "charset": "字符编码",
    "dependencies":"js依赖库地址(初始化加载js,建议在搜索源根目录创建)",
    "request": "请求链接@post->请求数据@header->请求头",
    "metadata": {
        "list": "使用js语言(默认Main为主函数名,函数参数html为网页源码,返回为数组)",
        "name": "使用js语言(默认Main为主函数名,函数参数text为每列源码)",
        "author": "使用js语言(默认Main为主函数名,函数参数text为每列源码)",
        "img": "使用js语言(默认Main为主函数名,函数参数text为每列源码)",
        "link": "使用js语言(默认Main为主函数名,函数参数text为每列源码)"
    },
    "detail": {
        "author": "使用js语言(默认Main为主函数名,函数参数html为网页源码)",
        "summary": "使用js语言(默认Main为主函数名,函数参数html为网页源码)",
        "upDate": "使用js语言(默认Main为主函数名,函数参数html为网页源码)",
        "catalog_link": "使用js语言(默认Main为主函数名,函数参数html为网页源码)",
        "tab": {
            "list": "使用js语言(默认Main为主函数名,函数参数html为网页源码,返回为数组)",
            "name": "使用js语言(默认Main为主函数名,函数参数text为每列源码)"
        },
        "catalog": {
            "list": "使用js语言(默认Main为主函数名,函数参数html为网页源码,返回为数组)",
            "chapter": {
                "list": "使用js语言(默认Main为主函数名,函数参数html为网页源码,返回为数组)",
                "name": "使用js语言(默认Main为主函数名,函数参数text为每列源码)",
                "link": "使用js语言(默认Main为主函数名,函数参数text为每列源码)",
                "orderBy": 0,//排列方式 0:顺序 1:倒序
                "category": 2//解析方式 1:链接 2:漫画解析 3:视频解析 4:小说解析
            }
        }
    },
    "content": {
        "list": "使用js语言(默认Main为主函数名,函数参数html为网页源码,返回为数组)",
        "link": "使用js语言(默认Main为主函数名,函数参数text为每列源码)",
        "mode": 1//翻页模式 1:普通模式(左滑) 2:日漫模式(右滑)
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
| name         | javaScript代码,返回为数组 | 是   | 搜索结果名称                 |
| author       | javaScript代码,返回为数组 | 是   | 搜索结果作者                 |



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
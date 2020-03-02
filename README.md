```json
{
    "type": "MyACG搜索源",
    "name": "搜索源名称",
    "summary": "搜索源介绍",
    "sources": "搜索源根目录",//搜索源根目录+搜索源名称+.json
    "versionName": "1.0",//搜索源版本名称
    "versionCode": 1,//搜索源版本(int范围内)
    "list": [
        {
            "name": "搜索源名称",
            "url": "域名(并未规范)",
            "checked": true,//默认开启
            "category": 1//解析方式 1:链接 2:漫画解析 3:视频解析 4:小说解析
        }
    ]
}
```
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
```js

jsoup语法:
https://github.com/json-path/JsonPath/blob/master/README.md

jsonPath语法:
https://github.com/json-path/JsonPath/blob/master/README.md

jsoup调试网站https://try.jsoup.org/

jsonPath调试工具https://github.com/zykzml7788/JsonPathUtil

js语言调用类

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
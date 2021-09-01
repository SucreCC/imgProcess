打开上面的地址，按F12开发者工具 - NetWork - XHR - 页面往下滑动XHR栏出现请求信息如下：

Request URL ：https://pic.sogou.com/napi/pc/searchList?mode=1&start=48&xml_len=48&query=%E7%BE%8E%E5%A5%B3

分析这段请求URL的主要几个参数：

start=48 表示从第48张图片开始检索

xml_len=48 从地48张往后获取48张图片

query=？搜索关键词（例：美女，这里浏览器自动做了转码，不影响我们使用）

图片
点击Respose，找个JSON格式器辅助过去看看。

图片
JSON格式：https://www.bejson.com/

分析Respose返回的信息，可以发现我们想要的图片地址放在 picUrl里，

图片
思路
通过以上分析，不难实现下载方法，思路如下：

设置URL请求参数
访问URL请求，获取图片地址
图片地址存入List
遍历List，使用线程池下载到本地![微信图片_20210901174539](https://user-images.githubusercontent.com/79621538/131651168-6e014419-71e0-42a7-a6b1-a64c5049e011.jpg)

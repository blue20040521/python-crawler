# prepare
## 安装（requests库）和简单测试
win+R + cmd,输入以下代码
```
pip install requests
```
测试是否安装成功，打开python，输入下面的代码
```python
import requests

# 发送一个简单的GET请求
response = requests.get("https://github.com/blue20040521")

# 打印响应内容
print(response.text)

```
你也可以根据你的需求，输入不同的代码，比如
```python
print(type(response)) # response 类型
print(response.text) # 内容
print(response.content) # 二进制内容(可用于获取视频、图片)
print(response.status_code) # 状态码
print(response.cookies) # cookie
```

## 带有参数的get
打开你的b站，你会发现上面的网址是这样的一串
```
https://www.bilibili.com/?spm_id_from=×××.××××.×.×
```
你可以理解为？后面的一堆都是查询字符串，spm_id_from是参数，×××.××××.×.×是参数值（可能根据你的账号和端口）
```python
import requests

response = requests.get("http://httpbin.org/get?name=germey&age=22")
print(response.text)
{
    "args": {
    "age": "22", 
    "name": "germey"
  }, 
    "headers": {
    "Accept": "*/*", 
    "Accept-Encoding": "gzip, deflate", 
    "Connection": "close", 
    "Host": "httpbin.org", 
    "User-Agent": "python-requests/2.18.4"
  }, 
  "origin": "183.64.61.29", 
  "url": "http://httpbin.org/get?name=germey&age=22"
}
```
或者使用params的方法：
```python
import requests

data = {
 'name': 'germey',
 'age': 22
}
response = requests.get("http://httpbin.org/get", params=data)
print(response.text)

```

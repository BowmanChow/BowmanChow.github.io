---
layout: post
title:  "Wifi 音响入侵"
date:   2021-05-12 12:25:45 +0000
categories: jekyll update
description: Wifi 音响入侵
---

## 嗅探

![](https://tech-1301874737.cos.ap-nanjing.myqcloud.com/hack/WifiSpeaker/packet_http.png)

![](https://tech-1301874737.cos.ap-nanjing.myqcloud.com/hack/WifiSpeaker/packet_music.png)

## 使用 python 发送请求获取数据

```python
client = socket.socket()
data = '''GET /audio/b5fe20b84aaf0508fdc68ee87ad993a5.mp3 HTTP/1.1\r\nAccept: */*\r\nAccept-Language: zh-cn\r\nUser-Agent: Molliza/4.0(compatible;MSIE6.0;windows NT 5.0)\r\nHost: resources.hivoice.cn\r\nConnection: close\r\nRange: bytes=0-\r\n\r\n'''
client.connect(('resources.hivoice.cn', 80))
client.send(data.encode())
img_data = bytes('','utf-8')
res = client.recv(1024)
```

获取音频
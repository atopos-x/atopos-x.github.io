---
title: cloudflare
aliases: 
tags:
  - _Misc
date: 2024-11-10
lastmod: 
time: 16:18
---
## 错误
>::重定向次数过多

![](../assets/Pasted%20image%2020241110170055.png)
需要进入到cloudflare，找到使用的域名，打开，然后找到SSL/TLS->概述，将加密模式改为完全，之后强制刷新`ctrl + shift + r`
## 使用Cloudflare的 Workers来实现监控网站标题
以下是实现这一方法的简要步骤：

1. 首先，在Cloudflare的控制台中创建一个新的Worker。

2. 在Worker代码编辑器中粘贴以下代码：

```javascript
addEventListener('fetch', event => {
  event.respondWith(handleRequest(event.request))
})

async function handleRequest(request) {
  const url = 'YOUR_WEBSITE_URL'; // 你想要监控的网站地址
  const response = await fetch(url);
  
  if (!response.ok) {
    return new Response('Website is down', { status: 500 });
  }

  const text = await response.text();
  const title = text.match(/<title[^>]*>([^<]+)<\/title>/i)[1];

  return new Response(`Title: ${title}`, { status: response.status });
}
```

3. 替换代码中的`YOUR_WEBSITE_URL`为你要监控的网站地址。

4. 点击保存并部署Worker。

5. 现在，你可以通过Worker的URL来访问监控网站标题的结果。如果网站不可用，将返回"Website is down"，否则将返回网站的标题。

这样，你就可以使用Cloudflare的Workers来监控网站的标题了。



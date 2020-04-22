### 1.Sanic简介

> Sanic是一个Python 3.6+web服务器和web框架，编写起来非常快。它允许使用Python 3.5中添加的async/await语法，这使您的代码无阻塞且快速。

### 2.安装

`pip install sanic`

### 2.简单入门

`main.py`

```python
from sanic import Sanic
from sanic.response import json

app = Sanic()

@app.route("/")
async def test(request):
  return json({"hello": "world"})

if __name__ == "__main__":
  app.run(host="127.0.0.1", port=8000)
```

`python3 main.py`启动后，打开浏览器[http://localhost:8000](http://localhost:8000)可以查看结果，是不是非常简单呢。


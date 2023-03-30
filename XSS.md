Exploit Title: There is a cross-site scripting attack in OTCMS that needs authentication

Vendor Homepage: http://otcms.com/

Software Link: http://otcms.com/news/7856.html ; http://d.otcms.com/php/OTCMS_PHP_V6.72.zip

Version: 6.72

Vulnerability:

Enter the system background as an administrator

Admin can edit page in 常规设置(General settings) --> 单篇页管理(Single page management):  
![image](https://user-images.githubusercontent.com/98327377/228747795-92da371c-d013-4cdc-b27d-2b0a42f23471.png)

the cross-site scripting vulnerability is in 标题(title) 

payload:<script>alert(1)</script>

When the page is saved, the vulnerability will be triggered

![image](https://user-images.githubusercontent.com/98327377/228750224-21743d6c-1657-4e00-b544-b24267fde2f3.png)

When user go the page, the vulnerability will also be triggered, it's a Stored Cross-site Scripting

![image](https://user-images.githubusercontent.com/98327377/228750285-a7076b34-2bf0-4de6-8109-1314134416dc.png)

![image](https://user-images.githubusercontent.com/98327377/228751592-cfb67ccc-192f-4022-a06f-2fc491df5628.png)

And it also works in the 管理员区(Administrator area) --> 后台操作日志(Background operation log),

![image](https://user-images.githubusercontent.com/98327377/228750379-555d5d39-4c94-4532-8938-b0f425d1b56c.png)

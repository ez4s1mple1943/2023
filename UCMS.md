## UCMS_v1.6.0 Stored Cross-site Scripting Vulnerability

vendor: [http://uuu.la/](http://uuu.la/)

UCMS 1.6 installation package： http://uuu.la/uploadfile/file/ucms_1.6.zip

Vulnerability type：

V 1.6.0

Recurrence environment：

Windows 10

phpstudy

Vulnerability description：

The vulnerability lies in /ucms/str/index.php file, the data entered by admin is not filtered

Loophole recurrence：

`/ucms/str/index.php`    There is no filter and not using htmlspecialchars. And go to htmlinput.

![](C:\Users\yaoyongbo\AppData\Roaming\marktext\images\2023-03-30-16-01-40-image.png)

So if attacker can login as admin, in 站点管理(Site management ) --> 站点设置(Site Settings)  attacker can edit the site settings

![](C:\Users\yaoyongbo\AppData\Roaming\marktext\images\2023-03-30-16-09-59-image.png)

The vulnerability is in 备案号  and 统计代码

![](C:\Users\yaoyongbo\AppData\Roaming\marktext\images\2023-03-30-16-13-58-image.png)

![](C:\Users\yaoyongbo\AppData\Roaming\marktext\images\2023-03-30-16-16-30-image.png)

After submit, anyone who goes to the home page will trigger the vulnerability twice

![](C:\Users\yaoyongbo\AppData\Roaming\marktext\images\2023-03-30-16-18-39-image.png)

![](C:\Users\yaoyongbo\AppData\Roaming\marktext\images\2023-03-30-16-18-51-image.png)

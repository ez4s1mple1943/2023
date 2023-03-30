## UCMS_v1.6.0 Stored Cross-site Scripting Vulnerability

vendor: [http://uuu.la/](http://uuu.la/)

UCMS 1.6 installation package： http://uuu.la/uploadfile/file/ucms_1.6.zip

Vulnerability type：

v1.6.0

Recurrence environment：

Windows 10

phpstudy

Vulnerability description：

The vulnerability lies in /ucms/str/index.php file, the data entered by admin is not filtered

Loophole recurrence：

`/ucms/str/index.php`    There is no filter and htmlspecialchars.

```
<?php
$strarray=explode('|',$link['strarray']);
$thisinput=array(
	'id'=>$link['id'],
	'from'=>'str',
	'pictips'=>$link['strtip'],
	'kind'=>$link['inputkind'],
	'inputname'=>'input_'.$link['id'],
	'inputvalue'=>$link['strvalue'],
	'style'=>$link['strstyle'],
	'strarray'=>$strarray
);
htmlinput($thisinput);
	echo(' '.$link['strtip']);
?>
```
![image](https://user-images.githubusercontent.com/98327377/228776441-800f7d9f-ae6b-434e-a347-f4d4a74b2e02.png)

So if attacker can login as admin, in 站点管理(Site management ) --> 站点设置(Site Settings)  attacker can edit the site settings. The vulnerability is in 备案号  and 统计代码

![image](https://user-images.githubusercontent.com/98327377/228776186-7e9817ab-2c6d-410d-8e5c-3fd676dd5df0.png)

After submit, anyone who goes to the home page will trigger the vulnerability twice

![image](https://user-images.githubusercontent.com/98327377/228776628-f7718605-fa29-4410-b8c6-4dc08698f7bd.png)

![image](https://user-images.githubusercontent.com/98327377/228776660-d9d02bc6-deae-4de3-94e5-1e146da4631b.png)

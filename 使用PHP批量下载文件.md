```php
<?php
ignore_user_abort(true);
set_time_limit(0);
/*
这是我的第一个文件备注名,http://down.url.com/english.filename1.zip
这是我的第二个文件备注名,http://down.url.com/english.filename2.zip
*/
$data='';
$data=file_get_contents('cssmoban_wpthemes.csv');
$data=explode("\n", $data);
$_last_data=[];
foreach ($data as $v) {
	$_last_data[]=explode(",", $v);
}
foreach ($_last_data as $cell) {
	echo trim($cell[0]).trim(basename($cell[1]))."\n";
	$file_data=file_get_contents($cell[1]);
	file_put_contents(trim($cell[0]).trim(basename($cell[1])), $file_data);
}
```
> 你不用完全按照我上面的例子，它如[云盘批量下载](https://github.com/clh021/diary/blob/master/%E5%A6%82%E4%BD%95%E8%AE%A9%E4%BA%91%E7%9B%98%E6%89%B9%E9%87%8F%E4%B8%8B%E8%BD%BD.md)一样，都是提供一个思路给你。

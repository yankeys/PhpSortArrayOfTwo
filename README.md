# PhpSortArrayOfTwo
只上传了同结构的二维数组排序。。。

##方法一：

```php
        $reArr = [];
        foreach ($items as $v) {
            $reArr[$v[$column]] = $v;
        }
        ksort($reArr);
```
###        缺陷：
####       每一个二维数组键改变成了需要进行对比的值
        
         
##方法二： 
```php
        $reArr = [];
        foreach ($items as $key => $v) {
            $reArr[$key]  = $v['time'];
        }
        array_multisort($reArr, SORT_ASC, $items);
```        
###        缺陷：
####       无
####       且可以进行相同值得二级字段排序，详情: http://php.net/manual/zh/function.array-multisort.php

# PHP7-new-feature

#PHP7实用新特性

##运算符
####1、??
PHP5
<pre>
$a = isset($_GET['a']) ? trim($_GET['a']) : '';
</pre>

PHP7
<pre>
$a = $_GET['a'] ?? '';
</pre>

意思是如果存在`$_GET['a']`，就直接等于它，否则`??`后边的内容进行赋值<br/>
有点类似javascript中的`var a = opt || {}`

####2、<=>
PHP5
<pre>
function compare($a, $b) {
    return ($a < $b) ? -1 : (($a >$b) ? 1 : 0);
}
</pre>

PHP7
<pre>
function compare($a, $b) {
    return $a<=>$b;
}
</pre>
意思是前边的小就是-1，前边大就是1，相等的是0

####3、**
<pre>
echo 2 ** -3, PHP_EOL;		//0.125
echo 2 ** -2, PHP_EOL;		//0.25
echo 2 ** -1, PHP_EOL;		//0.5
echo 2 ** 1, PHP_EOL;		//2
echo 2 ** 2, PHP_EOL;		//4
echo 2 ** 3, PHP_EOL;		//8
</pre>

所以，`**`的作用就是三次方:`m³`
####4、\u{xxxx}
<pre>
echo "\u{6211}\u{7231}\u{4f60}";		//我爱你




























##PHP7实用新特性

###运算符
####1、??
PHP5
<pre>
$a = isset($_GET['a']) ? $_GET['a'] : '';
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
</pre>

###类型声明
####1、函数返回类型
<pre>
function getInt() : int {
    return 'test';
};
</pre>

//会报fatal
//PHP Fatal error:  Uncaught TypeError: Return value of getInt() must be of the type integer, string returned in /tmp/a.php:5


####2、函数入参类型
<pre>
function getAmount(int $num) : int {
    return $num;
}; 
getAmount('test');
</pre>
//上边传入字符串`test`会报致命错误<br/>
//PHP Fatal error:  Uncaught TypeError: Argument 1 passed to getAmount() must be of the type integer, string given, called in /tmp/a.php on line 7 and defined in /tmp/a.php:3


<pre>
declare(strict_types=1);	//严格模式下也会报错，改代码要放第一行
getAmount('123');
</pre>
//这里在严格模式下传入字符串`'123'`也会报错

###统一的语法变量
<pre>
$$foo['bar']['baz'];
</pre>

PHP5:$`($foo['bar']['baz'])`<br/>
PHP7:`($$foo)`['bar']['baz']





















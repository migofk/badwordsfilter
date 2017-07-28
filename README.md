# badwordsfilter
1- info<br>
php bad/swear words filter class. <br>
free swear words filter to use for anything.<br>
Language: English.<br>
424 swear words.<br>
it's a php class based on preg_replace() function.<br>
I got the array from badwords-master,a js filter.<br>
All the bad words will be replace with **** . you can change it with any thing you like just find the code below<br>
$this->post= str_ireplace($badwords, '****', $this->post);

2- how to use for laravel <br>
I created folder app/Classes and put badwordsfilter.php in it.<br>
Make sure befor the class name in badwordsfilter.php there is:  namespace App\Classes; <br>


How to call the class:<br>

//In a controller<br>
use App\Classes\badwordsfilter;<br>

//filtering a request.<br>

$title = new badwordsfilter($request->name);<br>

$post = post::create([<br>
             'name'=>$title->filter(),<br>
             'description'=>$request->description,<br>
             ...
]);<br>

// In a view<br>
//<?php <br>
$text = "fuck you tity bitch I'm the best in what I do";<br>
$filter2 = new App\Classes\badwordsfilter($text);<br>
echo $filter2->filter();<br> 
?><br>

You can use it for normal php pages just remove namespace App\Classes; <br>

correction, improving, updating are all welcomed!<br>

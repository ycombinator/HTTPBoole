HTTP Boole
==========
Framework to perform HTTP requests and perform boolean logic on their responses.

PHP Example 1 - Single URL
--------------------------
$u = HttpBoole.createUrl('http://www.yahoo.com');
if (HttpBoole.ok($u)) {
   echo "Yahoooooooo!";
}

PHP Example 2 - URI templates
-----------------------------
$ut = HttpBoole.createUrlTemplate('http://www.google.com?q={query}');
if (HttpBoole.ok($ut.bind('query', 'foobar'))) {
   echo "Yahoooooooo!";
}

PHP Example 3 - Disjunction
---------------------------
$u1 = HttpBoole.createUrl('http://www.yahoo.com');
$u2 = HttpBoole.createUrl('http://www.google.com');
if (HttpBoole.or($u1, $u2)) {
   echo "Yahoo or Google";
}


HTTP Boole
==========
Framework to perform HTTP requests and perform boolean logic on their responses.

2xx responses are treated as true.
4xx and 5xx responses are treated as false.

Currently only GET requests with no message bodies are supported.

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

TODO
----
* Implement the damn thing
   * Singleton for each URL.
   * Dependency tree formation for each boolean query.
   * Breadth-first traversal of tree with concurrent evaluation of nodes at each level.
   * Caching of responses within a single tree evaluation.
* Support message bodies
* Support POST requests


# PHP

I love PHP because it is such a low level website developing language, which brings everything with it. Most functions are easy to use, but the naming of most of the functions are aweful and the dollar sign still annoys me. Overall I enjoy writing code in PHP.


## Links 

* [PHP.net](<https://www.php.net/>) - Main site
* [PHP Manual](<https://www.php.net/manual/en/>) - Documentation
* [W3 Schools - PHP Tutorial](https://www.w3schools.com/php/default.asp) - Learning
* [Online PHP](https://onlinephp.io/) - Sandbox for testing PHP


## Types
## Enum
## String
## Functions
## Classes 


## Arrays (Dynamic)

<https://www.php.net/manual/en/ref.array.php>

``` php
// Create array
$array = [ 1, 2, 3 ];

// Get lenght and access elements
for ($i = 0; $i < count($array); ++$i) {
    $entry = $array[$i];
}

// Add, set and remove
array_push($array, 4);       // Add 4
$array[] = 5;                // Add 5
$array[0] = 11;              // Set 1 => 11
array_splice($array, 1, 1);  // Remove 2

// Find index
$index = array_search(3, $array);

// Debug print
var_dump($array);
``` 


## Associative Array (Dictionary)

<https://www.php.net/manual/en/ref.array.php>

``` php
``` 


## Noticable

``` php
// pathinfo()
```
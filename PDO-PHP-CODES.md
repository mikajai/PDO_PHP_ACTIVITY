# PDO_PHP_ACTIVITY


### Codes for dbConfig.php
```php
<?php

$host = "localhost";
$user = "root";
$password = "";
$dbname = "martinez"; #lastname
$dsn = "mysql:host={$host};dbname={$dbname}";

$pdo = new PDO($dsn, $user, $password);
$pdo->exec("SET time_zone = '+08:00';"); 

# to check if the dbConfig has no error and is successfully connected with the host server
if ($pdo){
    echo "connected successfully";
}
?>
```

## Codes inside index.php for numbers 3 - 8.

### Show codes demonstrating fetch_all(), use print_r, with "<pre>" tag in between.
```php
<?php require_once 'core/dbConfig.php'; ?> 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <?php

    // select everything from the shelter table
    $stmt = $pdo->prepare("SELECT * FROM shelter");
    
    // to check if the code is successfully executed
    if ($stmt->execute()){
        echo "<pre>";   // makes the output readable
        print_r($stmt->fetchAll()); // used to fetch everything 
        echo "<pre>";
    }
    else{
        echo "Query failed.";
    }
    ?>
</body>
</html>
```

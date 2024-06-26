# Working with HTML Forms and PHP scripts. 

### POST METHOD
In our example here, we print an input that came from our form. We'll be using the POST method. The POST method is used to send data to the server. 

```php
<?php

// Check if the form is submitted
if(isset($_POST['submitName'])) {

	// Get the value of the 'username' input field from the form  
	$username = $_POST['username'];

	// Display the username in an h2 heading 
	echo "<h2>Welcome to PHP," . $username. "!</h2>";  
}
?>

<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Document</title>
</head>
<body>

	 <!-- The form submits to the same page using the POST method -->
	<form action="index.php" method="POST">

		<!-- Input field for the username. Take note of the value stored in the name attribute -->
		<p><input type="text" placeholder="Type your name here!" name="username"></p>

		<!-- Submit button -->
		<p><input type="submit" value="Submit" name="submitName"></p>
	</form>
</body>
</html>
```

### GET METHOD

The GET method is used to request data from a specified resource. The data passed using the GET method is visible in the query parameters in the browser URL. 

Create an ```index.php``` file containing this PHP code. 

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Document</title>
</head>
<body>

	 <!-- The form submits to the same page using GET method -->
	<form action="testGet.php" method="GET">

		<!-- Input field for the username. Take note of the value stored in the name attribute -->
		<p><input type="text" placeholder="Type your name here!" name="username"></p>

		<!-- Submit button -->
		<p><input type="submit" value="Submit" name="submitName"></p>
	</form>
</body>
</html>
```

And then, create the ```testGet.php``` file.

```php
<?php  
if(isset($_GET['submitName'])) {

	// String passed inside our GET variable comes from the name attribute of our input element 

	$username = $_GET['username'];
	echo "<h1> From a get request: " . $username . "</h1>";
}
?>
```

### Adding Two Numbers
For this example, we'll add two numbers using GET method. Paste the code below on your ```index.php``` file. 

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Document</title>
</head>
<body>

	 <!-- The form submits to the same page using GET method -->
	<form action="testGet.php" method="GET">

		<!-- Input field for the username. Take note of the value stored in the name attribute -->
		<p><input type="text" placeholder="num 1 here" name="num1"></p>
		<p><input type="text" placeholder="num 2 here" name="num2"></p>

		<!-- Submit button -->
		<p><input type="submit" value="Submit" name="getSum"></p>
	</form>
</body>
</html>
```

```testGet.php```
```php
<?php  
if(isset($_GET['getSum'])) {

	// String passed inside our GET variable comes from the name attribute of our input element 
	$num1 = $_GET['num1'];
	$num2 = $_GET['num2'];

	// Create a variable to store the sum.
	$sum = $num1 + $num2;

	// Print the result
	echo "<h2>The answer is " . $sum . "</h2>";
}
?>
```





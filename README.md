<?php 

$host='localhost';
$user='root';
$pass='';
$db='registration';
$con=mysqli_connect($host,$user,$pass,$db);
if(isset($_POST['submit']))
{
	$name=$_POST['name'];
	$email=$_POST['Email'];
	$phone=$_POST['phone'];
	echo $name.'<br>'.$email.'<br>'.$phone;
	$sql="insert into user(name,email,phone) values('".$name."','".$email."','".$phone."')";
	mysqli_query($con,$sql) or die("SQL ERROR");
}




?>

<form method="post" action="test.php">
<input type="text" name="name" placeholder="Enter Name" value="" required>
<input type="email" name="Email" placeholder="abc@xyz.com" value="" required>
<input type="number" name="phone" placeholder="10 digit only" value="" required>


<input type="submit" name="submit" value="Submit">
</form>

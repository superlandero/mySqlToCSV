mySqlToCSV
==========

Class to convert a mySQL query to a CSV File on PHP

Example:

<?php
	require 'mySqlToCsv.php';
	
	$host = '127.0.0.1';
	$port = '3306';
	$server = $host . ':' . $port;
	$user = 'root';
	$password = 'root';
	$database = 'DB_NAME';
	
	$link = mysql_connect ($server, $user, $password);
	if (!$link)
	  die('Error: Could not connect: ' . mysql_error());
	
	mysql_select_db($database);
	$query = 'select * from TABLE_NAME';
	$result = mysql_query($query);
	
	//Output As String
	echo sqlToCsv::toStr($result, "<br />");

	//Output As File
	echo sqlToCsv::toFile($result, "EjemploCSV");
	
	mysql_close ($link);
?>
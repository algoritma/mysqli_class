# mysqli_class
Easy mysqli db class for MySQL + MariaDB

//https://codeshack.io/super-fast-php-mysql-database-class/?PageSpeed=noscript

$db = new db($DB_host, $DB_user, $DB_pwd, $DB_name, $DB_port);
//db select
$db->selectDB($dbName);

//BeginTrans
$db->autocommit(FALSE);
//query
$db->rollback();
//or
$db->commit();

$db->close();



$insert = $db->query("INSERT INTO tableName
          (column1, column2)
          VALUES (?, ?) ",
          array(arg1, arg2) );
//if insert then last insert id
$insert->lastInsertID();
//insert or update or delete
$insert->affectedRows();

//
$check = $db->query("SELECT columnName
          FROM tableName
          WHERE id=? ",
          array($id) )->fetchArray();
$result= $check['columnName'];
      
//query_count
$db->query_count

$result = $db->dLookUp("tableName", "columnName", "id= ?", ($id));


<?php
       $username=$_POST("username");
       $password=$_POST("password");
       $login=$_GET["login"];
        setcookie("username","$username",time()+86400);
       if($login=='yes')
       {
        $con=mysql_connect("localhost","root","");
        mysql_select_db("login");
        $get=mysql_query("SELECT count(id) FROM login WHERE user='$username' and pass='$password'");
        $result=mysql_result($get,0);
        if($result!=1)
        {
        echo "Invalid login.";
        }else{
        echo "Login Successful.welcome back". $COOKIE['username']."sir/madam";
        $_SESSION['username']=$username;
        }
     }
?>
        

# Captcha
PHP script that generates an alphanumeric captcha.

# How to use
Import the script [captcha.php](https://github.com/alecosa/captcha/blob/main/captcha.php) in the form where you want to insert the captcha.


Example:

```php
<?PHP
echo("
<!DOCUMENT TYPE='es'>
<html lang='es'>
    <head>
        <title>Captcha</title>
    </head>
    <body>
        <form method='POST' action='validar.php'>
        <table border=0 width='100%'>
        <tr>
");
require_once 'captcha.php';
echo("
        <tr>
        <td><button>Validar</button>
        </table>
        </form>
    </body>
</html>
");
?>
```

Subsequently, in the file that captures the form information (in the previous example it is validar.php), validate that the fields $captcha_random and $captcha_digitado are equal.

Example:

```php
<?PHP
$captcha_random=$_POST["captcha_random"];
$captcha_digitado=$_POST["captcha_digitado"];

if($captcha_random==$captcha_digitado){
    // Realizar operación correspondiente si el captcha es correcto
}else{
    echo("El captcha no corresponde");
}
?>
```

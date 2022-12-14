# SSN Funnel Tutorial

Thank you for your trust in SSN, you will not regret it.

Customer Information:
Username: ``
License key: ``
Compiled on: ``
Version #: ``

# Suggested specs and details

Operating System: `Ubuntu 20.04`
Ram: `1 Gb`
CPU: `1 core` @ `1 Ghz`
Absolute minimum Storage: `3 Gb`

# How To Setup SSN Funnel

SSN Funnel uses a MySQL database so you need to setup a database.

*   Upload the "FUNNEL" folder that you received in the "APIFUNNEL.zip" onto your server.

0.  `sudo apt-get update -y && sudo apt-get upgrade -y`
1.  `sudo apt-get install php apache2 phpmyadmin mysql-server mysql-client -y`
        * On the first screen, click the enter key with the first option selected "apache2"
        * On the second screen, click the enter key with the first option selected "<Yes>"
        * On the third screen, input a 32 character varchar password ending in "!?" such as "4guWEDLGS67PJhXm2sD7xQks7PF8PzuQ!?"
2.  `sudo ln -s /usr/share/phpmyadmin/ /var/www/html`
3.  `sudo mysql`

	When setting up the database replace the variables. Put these variables in the "config.json" file as well.

	Example variables:

	{DB_TABLE} -> SSNFUNNEL
	{DB_USERNAME} -> cooluserlol
	{DB_PASSWORD} -> 32 character varchar password ending in "!?" such as "4guWEDLGS67PJhXm2sD7xQks7PF8PzuQ!?"

	Note: For "{DB_FILEPATH}", enter the path to where your "database.sql" is located.

	{DB_FILEPATH} -> /root/FUNNEL/assets/database.sql
	
		CREATE DATABASE {DB_TABLE};
		CREATE USER '{DB_USERNAME}'@'localhost' IDENTIFIED BY '{DB_PASSWORD}';
		GRANT ALL PRIVILEGES ON * . * TO '{DB_USERNAME}'@'localhost';
		FLUSH PRIVILEGES;
		use {DB_TABLE};
		source {DB_FILEPATH}; 
		exit

*  Navigate into the directory that the "assets" folder is in by using: `cd "your directory"`.

4. `sudo service apache2 stop`
5. `chmod 777 *`

# How to run SSN Funnel

6. `./FUNNEL`

# How to screen SSN Funnel

7. `screen -S FUNNEL ./FUNNEL`

# How to deattach from the screen

8. Press keys: `CTRL` + `A` + `D` to detach from screen.

# How to reattach back into the screen

9. `screen -r FUNNEL`

# How to kill any screen that is running

10. `pkill screen`

# How to use SSN Funnel

9. http://YOUR_SERVER_IP/api/attack?username=&secret=&host=&port=&time=&method=

What variables can be used in the config file for "duration", "port", and "target"?

Target: {HOST}
Port: {PORT}
Duration: {TIME}
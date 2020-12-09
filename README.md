 #   WORDPRESS RUNBOOK ON UBUNTU 16.04 

1. **Install Linux VM** (YOU CAN REFER TO THE MANUAL)
2. **Install Apache2** (RESTART NETWORK AFTER WITH " sudo service networking restart")
3. **SSH to server on CMD** [ USER ]@[ IP ] -p [ PORT ]

4. **Install PHP/MYSQL SERVER** 
	4A. **Install PHP** 
	1.	 sudo add-apt-repository ppa:ondrej/php 
    2.	 sudo apt-get update
	3.	 sudo apt-get install php7.2
	
	4B. **Install MySQL** " sudo apt-get install mysql-server " ( "RECORD PASSWORD YOU CREATED" )

	4C. **Install required PHP mods/plugins**
	1.    sudo apt-get install libapache2-mod-php7.2
  	2.	  sudo apt-get install php7.2-mysql
  	3.	  sudo apt-get install php7.2-mbstring
	4.	  sudo apt-get install php7.2-mcrypt

	4B. **Install MySQL** " sudo apt-get install mysql-server " ( "RECORD PASSWORD YOU CREATED" )

	4C. **Install required PHP mods/plugins**
	1.    sudo apt-get install libapache2-mod-php7.2
  	2.	  sudo apt-get install php7.2-mysql
  	3.	  sudo apt-get install php7.2-mbstring
	4.	  sudo apt-get install php7.2-mcrypt

	4D. **Check status** of MySQL "sudo service mysql status"
	
	4E. **Restart MySQL** " sudo service mysql restart "

5. **Restart Apache2** " sudo service apache2 restart "

6. **Download WordPress (Using FTP/Curl)**
	6A. Navigate to where you want to install WP and download it with "curl -O       https://wordpress.org/latest.zip" 

	6B. **Install UnZip** " sudo apt-get install unzip "
	
	6C. **Run** _UnZip_ outside of the wordpress.zip directory to unzip the folder " unzip wordpress.zip "

7. **Restart Apache2** " sudo service apache2 restart "

8. **Check WordPress** to make sure it is working at " [ IP ADDRESS / WORDPRESS DIRECTORY NAME ] " in browser

9. **Check status of MySQL** with " sudo service mysql status"

10. **Create MySQL Database with _CMD_** ( **Run** " sudo apt-get install phpmyadmin " to install PHPMyAdmin " then use GUI to create DB )

	10A. **Run** " sudo mysql -u root -p " to access MySQL CMD and enter server password / MySQL password to enter
	
	10B.**Run** " CREATE DATABASE [ CHOOSE DBNAME ]; " to create a database
	
	10C. **Run** " CREATE USER '[ CHOOSE USERNAME ]'@'localhost' IDENTIFIED BY '[ CHOOSE PASSWORD ]' " " ; "
	
	10D. **Run** " GRANT ALL PRIVILEGES ON [ DBNAME ].* TO '[ USERNAME ]'@'localhost' " " ; "
	
	10E. **Run** " SHOW DATABASES " " ; " to check that the database was created
	
	10F. **Run** " FLUSH PRIVILEGES " " ; "
	
	10G. **Run** " exit " to exit MySQL CMD
	
11. **Restart Apache2 / MySQL** " sudo service mysql restart " " sudo service apache2 restart "

12. **Navigate to** " [ IP ADDRESS / WORDPRESS DIRECTORY NAME ] " in browser and enter database details 

	12A. **Enter** [DBNAME ] in the Database Name field
	
	12B. **Enter** [ DB USERNAME ] in the Username field
	
	12C. **Enter** [ DB PASSWORD ] in the Password fieldFirst
	
	12D. **Enter** [ localhost ] in the Database Host field ( should be already filled )
	
	12E. **Enter** [ wp_ ] in the Table Prefix field ( should be already filled)
	
	12F. **_Click Submit_**

13. **_WordPress_** will tell you to copy the provided details to [ wp-config.php ] file

	13A. **Navigate to WordPress directory** and " ls " to view contents ( you see the [ wp-config-sample.php file ] )
	
	13B. **Run** " sudo nano wp-config.php " to create new config file #* OR *# " sudo cp wp-config-sample.php wp-config.php " to copy sample file 
	
	13C. **Copy text provided by WordPress** install page and replace contents of [ wp.config ] file and save and exit file with //CRTL O// //ENTER// //CTRLX//

14. **_Refresh WordPress install screen_**

15. You should be taken to the [ **Welcome** ] page where you can create a [ site title ],[ username ] and [ password ] for you WordPress site. You must also add an [ email ]

16. **Click** [ Install Wordpress ] and you are done!

# NICE WORK YOU MADE IT.

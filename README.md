High-Pi-Temp
===========

Step 1: 
___
Connect your D18S20 to your Raspberry Pi and load the One-Wire D18S20 kernel modules.
Also you have to change the RAM address of your D18S20 in the temp.py file.



Step 2: 
___
Create a cronjob
        
    sudo crontab -e
    
Add the following line:

    * * * * * echo `date +\%d/\%m/\%Y-\%H:\%M:\%S`,`python "Add your project directory"/temp.py` >> "Add your project directory"/temp.log
         
The cronjob creates a log file and adds the current temperature and a timestamp every minute.


Step 3:
___
Go to your project directory and start the server with:

    nodejs staticserver.js
    
    
Step 4:
___
Open the following URL in your browser:

    http://ip-adress.of.your.pi:8080/temp_anim.html
        
        

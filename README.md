Usage 

I wrote this script to work with AWS EC2 or lightsail, but really it should work with just about any Ubuntu 24 machine with a public IP address (only tested on AWS though so your mileage may vary)
I wanted it to also create a local postgres database with the credentials stored in the .env file so that if necessary you can have one per machine for testing purposes, but if you have an external db then feel free to comment out the 2 "paragraphs"dedicated to this, and fill out your database details in the .env and settings files 

Create a new EC2 or lightsail instance with Ubuntu Server 24, allowing http and https traffick, and SSH from your IP address
Connect to it using SSH
If you have a domain name, change the A records in its DNS settings to point to the publiv IPV4 address of your instance

Clone this repository into the machine : `git clone https://github.com/Mickdevv/django_deploy_example.git` 
Enter the script's directory : `cd django_deploy_example/example_app/`
Change the permissions of the file to allow for execution : `chmod +x deploy_django.sh`
Now let her rip! : `./deploy_django.sh <optional domain name>`

At the end, you should have an output like 

Some important notes if you want to use this in your own project :

1. The .env file is used for sentitive information, NEVER hard code your secrets
2. The settings.py file has been changed to reflect the above point using the python-dotenv package to fetch data from the .env file
3. The username in the script is ubuntu by default, please be sure to check that it is the right one on your machine
4. You will want to replace the example requirements.txt file with your own to ensure you have all the necessary packages (you can do so with the `pip freeze > requirements.txt` command from your project's python environment), but make sure you also keep those already in the example one as they are necessary for this script to work

Happy deployment ! :) 

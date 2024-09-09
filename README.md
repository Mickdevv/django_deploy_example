Usage/Utilisation

--- EN ---

I wrote this script to work with AWS EC2 or lightsail, but really it should work with just about any Ubuntu 24 machine with a public IP address (only tested on AWS though so your mileage may vary)
I wanted it to also create a local postgres database with the credentials stored in the .env file so that if necessary you can have one per machine for testing purposes, but if you have an external db then feel free to comment out the 2 "paragraphs" dedicated to this, and fill out your database details in the .env file
If you don't yet have a domain name that's okay ! Run the script without one and you can access the app by entering the server's public IP address into your browser, or simply clicking the helpful link shown in the console at the end of the script.

Create a new EC2 or lightsail instance with Ubuntu Server 24, allowing http and https traffick, and SSH from your IP address
Connect to it using SSH
If you have a domain name, change the A records in its DNS settings to point to the publiv IPV4 address of your instance

1. Clone this repository into the machine: `git clone https://github.com/Mickdevv/django_deploy_example.git`
2. Enter the script's directory: `cd django_deploy_example/example_app/`
3. Change the permissions of the file to allow for execution: `chmod +x deploy_django.sh`
4. Now let her rip! : `./deploy_django.sh <optional domain name>`
5. Go grab a coffee or other beverage of choice, this will take a few minutes
6. When the script gets to the firewall settings, you will get a promt like `Command may disrupt existing ssh connections. Proceed with operation (y|n)?`. Check out the firewall settings in the script if you want to see them. If you're happy with them, type y and press enter.

At the end, you should have a clickable link either to the domain name of the website or its public IP address if youdidn't enter one.

Some important notes if you want to use this in your own project:

1. The .env file is used for sentitive information, NEVER hard code your secrets
2. The settings.py file has been changed to reflect the above point using the python-dotenv package to fetch data from the .env file
3. The username in the script is ubuntu by default, please be sure to check that it is the right one on your machine
4. You can use your own requirements.txt file (you can create it with the `pip freeze > requirements.txt` command from your project's python environment). The script has its own pip install to install the packages it needs to work

Happy deployment! :) 

--- FR ---

J'ai écrit ce script pour fonctionner avec AWS EC2 ou Lightsail, mais en réalité, il devrait fonctionner avec à peu près n'importe quelle machine Ubuntu 24 avec une adresse IP publique (testé uniquement sur AWS, donc votre expérience peut varier).

Je voulais qu'il crée également une base de données Postgres locale avec les identifiants stockés dans le fichier .env, afin que, si nécessaire, vous puissiez en avoir une par machine à des fins de test. Cependant, si vous avez une base de données externe, vous pouvez commenter les deux "paragraphes" dédiés à cette fonctionnalité et remplir les détails de votre base de données dans le fichier .env.

Si vous n'avez pas encore de nom de domaine, pas de souci ! Exécutez le script sans en spécifier un, et vous pourrez accéder à l'application en entrant l'adresse IP publique du serveur dans votre navigateur, ou simplement en cliquant sur le lien pratique affiché dans la console à la fin du script.

Créez une nouvelle instance EC2 ou Lightsail avec Ubuntu Server 24, en autorisant le trafic SSH depuis votre adresse IP, et puis HTTP et HTTPS. Connectez-vous à l'instance via SSH. Si vous avez un nom de domaine, modifiez les enregistrements A dans les paramètres DNS pour qu'ils pointent vers l'adresse IPv4 publique de votre instance.

1. Clonez ce repo sur la machine : `git clone https://github.com/Mickdevv/django_deploy_example.git`
2. Entrez dans le répertoire du script : `cd django_deploy_example/example_app/`
3. Modifiez les permissions du fichier pour permettre son exécution : `chmod +x deploy_django.sh`
4. Lancez-le : `./deploy_django.sh <nom de domaine optionnel>`
5. Prenez un café ou une autre boisson de votre choix, cela prendra quelques minutes !
6. Lorsque le script arrive aux paramètres du pare-feu, vous verrez une invite comme celle-ci : `Command may disrupt existing ssh connections. Proceed with operation (y|n)?`. Consultez les paramètres du pare-feu dans le script si vous souhaitez les vérifier. Si vous êtes satisfait, tapez y et appuyez sur Entrée.

À la fin, vous devriez avoir un lien clickable vers soit votre nom de domaine renseigné, soit l'addresse public de votre serveur.

Quelques points importants si vous souhaitez utiliser ce script dans votre propre projet :

1. Le fichier .env est utilisé pour les informations sensibles, NE JAMAIS coder en dur vos secrets.
2. Le fichier settings.py a été modifié pour refléter ce point, en utilisant le package python-dotenv pour récupérer les données du fichier .env
3. Le nom d'utilisateur dans le script est par défaut "ubuntu", veuillez vérifier que c'est bien celui utilisé sur votre machine.
4. Vous pouvez utiliser votre propre fichier requirements.txt (vous pouvez le créer avec la commande `pip freeze > requirements.txt` depuis l'environnement Python de votre projet). Le script possède sa propre installation pip pour installer les packages nécessaires à son fonctionnement.

Bon déploiement ! :)

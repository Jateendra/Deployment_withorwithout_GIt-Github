# Deployment_withorwithout_GIt-Github

This is a simple web application using [Python Flask](http://flask.pocoo.org/) and [Pythonanywhere cloud platform ](https://www.pythonanywhere.com/) . 
Have demonstrated here how to use the Flask application with and without using Github to deploy the application in Web .

## Initial Steps :
   
1 . Design a flask application using VS Code.
	
	Project Name : Deployment_withorwithout_GIt-Github

2 . In Gitbash , perform the below steps :

	install the Libraries & try to run the app :
	
	pip install -r requirements.txt
	flask run
	
	Commit the code :
	
	git init
	git add .
	git commit -m "Jateen first commit"

3 . Open Github  :

Create a repository named "Deployment_withorwithout_GIt-Github"

	git remote add origin https://github.com/Jateendra/Deployment_withorwithout_GIt-Github.git
	git branch -M main
	git push -u origin main
	
## Deploy the code with Github :

	
4 . Go to URL : https://www.pythonanywhere.com/

If you don't have an account , follow below steps :

	Pricing -> Create a Beginner account
	
If you already have an account :

	Consoles -> Bash
	git clone https://github.com/Jateendra/Deployment_withorwithout_GIt-Github.git
	
	** Incase if it asks for password/token
	Go to github -> profile -> Settings -> Developer Settings -> Personal access tokens -> Generate new token -> Generate
	Copy and paste the token in the above console .
	
	mkvirtualenv venv --python=python3.7
	ls -lrt
	cd  Deployment_withorwithout_GIt-Github
	ls -lrt
	pip install -r requirements.txt
	
Click on top right hand corner 3 dash hamburger .

	Web -> Add a new web app -> next -> Manual configuration (including virtualenvs) -> Python 3.7 -> Next 
	Virtualenv : venv
	Code -> Source Code : Deployment_withorwithout_GIt-Github 
	WSGI file configuration :
		- delete the code from " HELLO World  till def application().."
		- activate the below peice of code : 
			import sys
			path = '/home/Jateendra/Deployment_withorwithout_GIt-Github '
			if path not in sys.path:
				sys.path.append(path)

			from app import app as application  # noqa
		
	Come back to the main page -> Reload -> Click the URL	
	Force HTTPS: -> Make it enable -> Reload -> Click the URL	( It creates the URL safe )
	
## Deploy the code without Github :

Before doing this action "Delete Jateendra.pythonanywhere.com" project . 

  - Click on Web -> It will show 
  - Click on Files -> Delete all files

Now the procedure is to deploy directly from local system to pythonanywhere by drag-n-drop , no Gitbash or Github involvement .

	Web -> Add a new web app -> next -> Manual configuration (including virtualenvs) -> Python 3.7 -> Next
	Files -> Directories - > Enter New Directory Name : Deployment_withorwithout_GIt-Github -> Click on "New Directory"
		- Click on "Upload a file"
		- Upload files one by one , if requred create the folders also.
		- Even upload "requirements.txt" file
	Consoles -> Bash	
		mkvirtualenv venv --python=python3.7
		ls -lrt
		cd  Deployment_withorwithout_GIt-Github
		ls -lrt
		pip install -r requirements.txt
		
Click on top right hand corner 3 dash hamburger .

	Web -> Code -> Source Code : Deployment_withorwithout_GIt-Github 
	Virtualenv : venv
	WSGI file configuration :
		- delete the code from " HELLO World  till def application().."
		- activate the below peice of code : 
			import sys
			path = '/home/Jateendra/Deployment_withorwithout_GIt-Github'
			if path not in sys.path:
				sys.path.append(path)

			from app import app as application  # noqa
		
	Come back to the main page -> Reload -> Click the URL	
	Force HTTPS: -> Make it enable -> Reload -> Click the URL	( It creates the URL safe )
  
                                                            ## Happy Learning ##

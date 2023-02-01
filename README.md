# Setup-mongoDB-on-Linux
# To start, import the public GPG key for the latest stable version of MongoDB by running the following command and it will show "ok":
	wget -qO - https://www.mongodb.org/static/pgp/server-6.0.asc | sudo apt-key add -
# However, if you receive an error indicating that gnupg is not installed, run these command
	sudo apt-get install gnupg
	wget -qO - https://www.mongodb.org/static/pgp/server-6.0.asc | sudo apt-key add -
	
# If you’d like to double check that the key was added correctly, you can do so with the following command:
	apt-key list
# Create a list file for MongoDB:
	echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-6.0.list
	
# Reload local package database:
	sudo apt-get update
# To install latest version of mongoDB by running the following command:
	sudo apt install mongodb-org
	
# To run mongoDB service run the following systemetical command
	sudo systemctl start mongod.service
	
# Then check the service’s status
	sudo systemctl status mongod
	
# To install the latest stable version of mongosh, issue the following command:
	sudo apt-get install -y mongodb-mongosh
	
# After confirming that the service is running as expected, to enable mongoDB isshue the following command:
	sudo systemctl enable mongod
	
# To get access or to see db related task isshu the following command:
	mongosh

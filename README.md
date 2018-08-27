# Linux Server Configuration
This project is about the complete configuration and customization of an ubuntu 
linux instance to host the [catalog](https://github.com/albertodepaola/catalog-project) 
application. In particular, the branch used in this server is named '**project-5**'.  

## Logging in
The public ip address is 104.248.48.163 and the domain used to configure Google's
OAuth is [http://104.248.48.163.xip.io](http://104.248.48.163.xip.io). The SSH port 
is 2200 and grader is configured as sudoer. The private key will be pasted in
the project submission notes.



## Configuration

Steps followed to complete this assignment:
  - Created an account on [DigitalOcean](https://www.digitalocean.com/) 
    - created 'droplet' with ubuntu 16.04 lts
    - configured the droplet's firewall
  - configured ufw to open port 2200, 80 and 123
  - changed default ssh port
  - installed `apache2` and `libapache2-mod-wsgi`
  - downloaded project with git
    - installed requirements with `pip install -r requirements.txt` (no virtualenv 
    this time)
  - configured default site 
  - configured apache folder permissions
  - added [dns](http://104.248.48.163.xip.io) to Google API credentials
  - installed and configured database (postgres)
    ```SQL
    create database catalog;
    create user catalog with encrypted password 'catalog';
    grant all privileges on database catalog to catalog;
    ```
    
  - added user and password in applications config file `config.py`
  - created grader user with api keys and sudo access
  
  ### TODO
  - change the current app directory to one located in a custom user
  
  ## References
  
  Here are some of the multiple links used to complete this project:
  - [Readme reference](https://help.github.com/articles/basic-writing-and-formatting-syntax/) 
  - [NTP configuration](https://geek-university.com/linux/configure-ntp-client/)
  - [Add linux user](https://www.digitalocean.com/community/tutorials/how-to-create-a-sudo-user-on-ubuntu-quickstart)
  - [Add keys to existing droplet](https://www.digitalocean.com/docs/droplets/how-to/add-ssh-keys/to-existing-droplet/)
  - [Creating postgres database and user](https://medium.com/coding-blocks/creating-user-database-and-adding-access-on-postgresql-8bfcd2f4a91e)
  - [Configuring apache to serve the app](http://www.devfuria.com.br/python/flask-apache/)
  - [Flask AppBuilder documentation](https://flask-appbuilder.readthedocs.io/en/latest/intro.html)
  - [wsgi.py content](https://github.com/dpgaspar/Flask-AppBuilder/issues/180)
  - [Reference for initial server setup](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-16-04)
  
  
# License
The content of this repository is licensed under a [Creative Commons Attribution License](https://creativecommons.org/licenses/by/3.0/us/)


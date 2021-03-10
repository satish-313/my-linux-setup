# my-linux-setup
my linuxos(ubuntu) set up after installing.

As I am new to ubuntu of linux system, some time making note will be easy to setup next time.

1. first thing when setting of a ubuntu system during installation time set an easy password for using sudo privilage. That password need every time we install sudo command and installing some software.

2. Then connect to internet update and connect to ubuntu repository using $ sudo apt update (then we can use apt to download some software).

3. Then download your favorite web browser(google chrome).
   1. Use wget to download google chrome latest .deb file ($ wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb)
   2. Use sudo to install google chrome (needed password use easier one) ($ sudo apt install ./google-chrome-stable_current_amd64.deb)
   3. It's done.

4. As a not expert web developer a good easy code editor will be good (vim is not my thing). VS code my choice of code editor.
   1. There are multiple way of install vscode most easy one use snap tool or download .deb file install sudo apt ./Download/vscode-file.deb
   2. These time I approach differently first set up a repository in apt and install with that one.
   3. get wget key ($ wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -)
   4. enable vscode repository ($ sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main")
   5. update the apt using ($ sudo apt update)
   6. after all setup install vscode using code key word ($ sudo apt install code)

5. A good version control will be helpful of any software developer. Git is my choice and must popular.
   1. sudo apt install git
   2. to check git version ($ git --version)

6. Installing nodejs in system
   1. we can use sudo apt install nodejs directly from ubuntu respository archive but it is out date some time some package need latest version of nodejs
   2. for that I follow the github of nodejssource page
   3. for that I used the curl (first install curl ($ sudo apt install curl))
   4. for the version I need replace the setup_15.x (replace 15.x to my need 12.x)
   ($ curl -fsSL https://deb.nodesource.com/setup_15.x | sudo -E bash -
sudo apt-get install -y nodejs)
   5. to check the version node -v and npm -v

7. Styling the ubuntu outlook using gnome extension
   1. install gnome-tweak-tool using $ sudo apt-get install gnome-tweak-tool. 
   2. to access the tool kit using gui install the extenstion in your choice browser, we can do it command line but i thing gui is better. $ sudo apt-get install chrome-gnome-shell
   3. goto https://extensions.gnome.org to install your packages

8. My ubuntu look
   1. to hide the trash icon from desktop ($ gsettings set org.gnome.shell.extensions.desktop-icons show-trash false)
   2. to hide the home from desktop (
   $ gsettings set org.gnome.shellextensions.desktop-icons show-home false)
   3. move the top panel to bottom panel using extension from gnome.org extenstion link

9. Install the postgresql in ubuntu (all infor from https://postgresql.org/download/linux/ubuntu/)
   1. create the file repository configuration: 
   ($ sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list')
   2. import the repository signing key:
   ($ wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add - )
   3. update the package lists:
   ($ sudo apt-get update)
   4. download the package:
   ($ sudo apt-get -y install postgresql-13)
   5. goto postgresql commad line 
   ($ sudo -i -u postgres ) to access postgres
   ($ psql ) to exit 
   ($ \q ) another way for me better way
   ($ sudo -u postgres psql)
   
10. Install python in ubuntu, on installing ubuntu it has ubuntu. But to use python we need type python3.
   1. It don't have the pip package we have to install using apt ($ sudo apt install -y python3-pip)
   2. for install any package use pip3 install<packagename>. we can create a venv file to use tradition way like python file.py or pip install <packagename>
   3. for rubost env file download some apt package using ($ sudo apt install -y build-essential libssl-dev libffi-dev python3-dev)
   4. Install venv(if not), ($ sudo apt install -y python3-venv). To create venv ($ python3 -m venv <env-name>). To activate the venv ($ source <env-name>/bin/activate)
   5. In env we can use pip and python command.

11. Install docker resource point (https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04)
   1. update the apt ($ sudo apt update)
   2. use curl to get docker repository ($ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -)
   3. add docker to repo ($ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable")
   4. update ($ sudo apt update)
   5. make use install docker repo instead of default ubuntu repo ($ apt-cache policy docker-ce)
   6. finally install docker (sudo apt install docker-ce)
   7. to check docker status ($ sudo systemctl status docker)
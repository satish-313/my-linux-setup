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


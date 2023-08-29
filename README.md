# ms-sql
install ms-sql on ubuntu 20.04

curl https://packages.microsoft.com/keys/microsoft.asc | sudo tee /etc/apt/trusted.gpg.d/microsoft.asc

sudo add-apt-repository "$(wget -qO- https://packages.microsoft.com/config/ubuntu/20.04/mssql-server-2022.list)"

sudo apt-get update
sudo apt-get install -y mssql-server

sudo /opt/mssql/bin/mssql-conf setup

systemctl status mssql-server --no-pager

sudo su

curl https://packages.microsoft.com/keys/microsoft.asc | sudo tee /etc/apt/trusted.gpg.d/microsoft.asc

curl https://packages.microsoft.com/config/ubuntu/20.04/prod.list > /etc/apt/sources.list.d/mssql-release.list

exit

sudo apt-get update
sudo apt-get install mssql-tools18 unixodbc-dev

#sudo apt-get update  
 sudo apt-get install mssql-tools18

echo 'export PATH="$PATH:/opt/mssql-tools18/bin"' >> ~/.bash_profile

echo 'export PATH="$PATH:/opt/mssql-tools18/bin"' >> ~/.bashrc
source ~/.bashrc

sqlcmd -S localhost -U sa -P '<YourPassword>'




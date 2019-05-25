
ISSUE : error message when running crypto generate tool 

cd fabric-samples/first-network
sudo ./byfn.sh generate


ERROR MESSAGE : cannot-find-cryptogen-tool-in-fabric


URL
###########################################
https://stackoverflow.com/questions/45564481/cannot-find-cryptogen-tool-in-fabric

From Above URL:

First I made sure that my fabric-samples folder was up to date, I'm unsure if this helped but here if anyone is trying to copy. I followed the steps here:


git clone -b master https://github.com/hyperledger/fabric-samples.git
cd fabric-samples
git checkout master
then running (replacing ubuntu with your username):



cd ~/Build-Multi-Host-Network-Hyperledger/
curl -sSL https://raw.githubusercontent.com/hyperledger/fabric/master/scripts/bootstrap.sh | bash -s 1.1.0

/ *  BELOW IS WHere there is an issue as this is whats recommended  and is outdated   */
curl -sSL https://goo.gl/6wtTN5 | bash -s 1.1.0
shortened URL: https://github.com/hyperledger/fabric/blob/master/scripts/bootstrap.sh
/*    */

export PATH=/home/ubuntu/Build-Multi-Host-Network-Hyperledger/bin:$PATH
( check path on local machine ) 
e.g export PATH=/c/Users/yinca/Documents/RADO/RAH/BLOCKCHAIN/PROGRAMMING/HYPERLEDGER/FABRIC_ENVIRONMENT/fabric-samples/bin:$PATH
( e.g again : export PATH=/home/ubuntu/Build-Multi-Host-Network-Hyperledger/bin:$PATH  )

Based on this, and how the problem was solved, probably run the updated version of user's script, and add that dir to the path.

Hopefully, this can help someone. 


#################################
Note

If you want the latest production release, omit all version identifiers.
curl -sSL http://bit.ly/2ysbOFE | bash -s 

(this is same as https://raw.githubusercontent.com/hyperledger/fabric/master/scripts/bootstrap.sh ) 

################################



################ WINDOWS ###############

to run fabric 

cd fabric-samples/first-network

./byfn.sh -m generate 

./byfn.sh -m up

./byfn.sh -m down

OTHER ISSUES 
#############

# Starting Docker 
--------------------------------

1. sudo apt-get install curl -y

2.sudo yum install curl -y
Use the command underneath to download the Docker image. The installation script requires root privileges so you will be asked for your sudo password on any non-root user.

3. curl -sSL https://get.docker.com/ | sh
After the installation finishes, Docker usually starts up on its own, but for the next part to work you will need to stop it.

4. sudo service docker stop

5. sudo systemctl enable docker

6. sudo nohup docker daemon -H tcp://0.0.0.0:2375 -H unix:///var/run/docker.sock &
The script leaves the daemon running in the background, and with the Docker ready you can test that it is accepting commands.

7. sudo docker info
To make working with Docker easier, you should add your username to the Docker users group. Adding a user to the group can be done with the command underneath by replacing the <username> with your username.

8. sudo usermod -aG docker remi 








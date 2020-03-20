# Kali-Linux-Development
01º - sudo su
02º - apt-get update
##Install node
03º - apt-get install python g++ make checkinstall fakeroot
04º - sudo apt update
05º - sudo apt -y install curl dirmngr apt-transport-https lsb-release ca-certificates
06º - curl -sL https://deb.nodesource.com/setup_10.x | sudo bash
07º - sudo apt update
08º - sudo apt -y install gcc g++ make
09º - sudo apt -y install nodejs
10º - curl -sL https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
11º - echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
12º - sudo apt-get update && sudo apt-get install yarn
##Install Chrome
13º - apt update
14º - wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
15º - apt install ./google-chrome-stable_current_amd64.deb
##Install Docker
16º - curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
17º - echo 'deb [arch=amd64] https://download.docker.com/linux/debian buster stable' | sudo tee /etc/apt/sources.list.d/docker.list
18º - sudo apt-get update
19º - sudo apt-get remove docker docker-engine docker.io
20º - sudo apt-get install docker-ce
#teste
21º - sudo docker run hello-world
22º - sudo systemctl start docker
23º - sudo systemctl enable docker
24º - sudo usermod -aG docker $USER
##install insomnia
25º - echo "deb https://dl.bintray.com/getinsomnia/Insomnia /" \ | sudo tee -a /etc/apt/sources.list.d/insomnia.list
26º - wget --quiet -O - https://insomnia.rest/keys/debian-public.key.asc \ | sudo apt-key add -
27º - sudo apt-get update
28º - sudo apt-get install insomnia
##install postBird
29º - sudo apt-get install gconf2 gconf-service libappindicator1
30º - baixe pckge site https://www.electronjs.org/apps/postbird
	.deb
31º - sudo dpkg -i Postbird_0.8.4_amd64.deb
32º - sudo apt-get install -f
##install mongoDb
33º - baixe o pckge mongoDbCompass site:https://www.mongodb.com/download-center/compass?tck=docs_compass
34º - sudo dpkg -i mongodb-compass_1.20.5_amd64.deb
35º - sudo apt-get install -f
##install visual studio code
36º - baixe o pckge https://code.visualstudio.com/docs/?dv=linux64_deb
37º - dpkg -i code_1.43.1-1584515895_amd64.deb
##

# reimagined-spoon
OSINT gathering tools for cyber threat analysis

AFter struggling to find a single docker-compose file that had OpenCTI and all the connectors I wanted in one compose file I finally made my own. Hopefully this makes life easier for other people. 

Prior to running the OpenCTI docker-compose file you will need to add:

vm.max_map_count=1048575

add this line to /etc/sysctl.conf, save and reboot. 


With a fresh Ubuntu Desktop or Server install run the following commands in terminal:

  sudo apt-get install docker-compose -y
  
  sudo docker volume create portainer
  
  docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data cr.portainer.io/portainer/portainer-ce:latest
  
  Access the portainer dashboard at https://localhost:9443, 
  Select Stacks
    Select Add Stack
      upload the docker-compose.yml file
      upload the opencti.env file
    Select Deploy the Stack
      Wait
      Login to http://localhost:8080
      
          
DON'T FORGET TO CHANGE THE DEFAULT CREDENTIALS AND ADD YOUR OWN API KEYS IN THE COMPOSE FILE

This stack was designed for an Ubuntu VM with 50GB of RAM and 16 CPU cores, adjust the replicas value for opencti/worker:latest as needed. 

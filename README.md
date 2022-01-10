# reimagined-spoon
OSINT gathering tools for cyber threat analysis

AFter struggling to find a single docker-compose file that had OpenCTI and all the connectors I wanted in one compose file I finally made my own. Hopefully this makes life easier for other people. 

Prior to running the OpenCTI docker-compose file you will need to add:

vm.max_map_count=1048575

add this line to /etc/sysctl.conf, save and reboot. 

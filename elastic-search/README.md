# Some simple ansible task for automating some of the tasks related to elastic search 

Requirement: 
    Update log4j2.properties on all elastic search servers, restart them and check if logs are being rolledand purged over or not
	
	
Use Case 1: 
   a) Take backup of existing log4j2.properties  if exists
   b) Update log4j2.properties of all the elastic search data and master nodes
   b) Restart elastic search  server
   
   
  playbook : 
      log4j-update.yml 
	  
  command:
     ansible-playbook  -i els-inventory.ini   log4j-update.yml 
   
   
Use Case  2: 
   a) Check whether elastic search service is up and running on all nodes or not,
   b) If an instance got terminated and ECS launced a new instance get the IP of that node
   
   playbook : 
       service-status.yml 
	  
   command:
      ansible-playbook  -i els-inventory.ini   service-status.yml


Use Case 3:
  a) Check whether logs are being rolled and purged over correctly 
  
  
  playbook : 
      log-rotation.yml
	  
  command:
     ansible-playbook  -i els-inventory.ini   log-rotation.yml
	 
  Note: USe case 3 will give you correct result only on next day.
  
  
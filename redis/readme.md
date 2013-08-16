Jumper API Redis Deployment Containers
=

Notes
-

-	Jumper is going to be running 5-10 different redis instances that can all live on their own
-	Each redis container should be its own docker file with the proper run commands etc
-	Each redis instance represents a dockerfile
-	The only between different redis instances is the  
-	We need to have a slave docker -- this is responsible for being booted with a master ip address /
	
	-	should take in a name upon boot so that we can set the glacier upload name
	-	the slave is responsible for backing itself up to glacier via cron 				
	-	possibly use a tool like maestro for this





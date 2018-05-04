# M3

## Team Members

   1. Rushi Bhatt - rbhatt
   2. Rutvij Mehta - rmehta4
   3. Vignesh Nandakumar - vnandak
   4. Zankruti Desai - zndesai
   
## Screencast and Description
  
### Deployment
 #### ![iTrust](https://youtu.be/Gm2saTsYAAs)
 #### ![checkbox.io](https://youtu.be/z951CzKFOEw) 
 - A git pre-push hook is triggered when a push to the checkbox.io or iTrust repository is attempted.
 - This hook btriggers the build of the jenkins job. 
 - Upon successful completion of the build job, as a post build task, we provision an EC2 instance and an ansible-playbook is run upon the instance to deploy the application on it.
 - We can access the application by visiting the IP address followed by port number on the browser.
           
### Infrastructure Upgrade
#### ![Redis](https://youtu.be/Sl73Osxfveg)
#### ![Nomad](https://youtu.be/Sl73Osxfveg)
- Load Balancer is implemented as a part of the infrastructure upgrade. 
- Plus, a master and slave paradigm of the redis servers has been created. 
- There is a master redis server in a container on its own. 
- And every instance is a result of a docker compose among the application, nginx server and a redis instance.
          
### Canary Release
#### ![checkbox.io Canary Release](https://youtu.be/G0tdpwKDwVc)
- We use multiple EC2 instances to demonstrate the working of the canary release.
- A load balancer is implemented to divert 60% of the traffic to the stable build.
- The remaining 40% of the traffic is routed to the Canary Build.
- At any point, when the canary server is taken down, the whole traffic is rerouted solely to the Stable build.
          
### Rolling Update
#### > ![iTrust Rolling Update](https://www.youtube.com/watch?v=bhJa1O_B_fE)
- We have deployed 5 instance of iTrust. 
- At each change we do a git push on which the git hook is triggered that 
would redeploy one instance while the other 4 instance remain operational.
- This way, at any instance of time, only one EC2 instance is not available for service.



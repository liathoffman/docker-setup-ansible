# docker-setup-ansible


What the playbooks do:

🦉 SET UP THE REPOSITORY
1. Install the required packages and update the package cache (steps 1 and 2)
2. Add docker’s official GPG key and Verify the key with the finger print (steps 3)
3. Add the repository (steps 4)
a. Tip: look at ansible_distribution fact to get the os distribution

🦉 INSTALL DOCKER ENGINE - COMMUNITY
1. Install the docker engine and update the package cache (steps 1 and 2)
2. Restart the docker service only if the docker engine package gets updates
3. Add ubuntu user to the docker group as in: sudo usermod -aG docker your-user
4. Edit the docker_setup.yml playbook you have created in class, add the following shell command to it- 
       `docker run -d -p 8080:80 nginx`
4. Run the playbook on your inventory - both nodes

To check your success: 
     - In AWS: Manually add a rule to the nodes' security group allowing access to it using port 8080
     - In your browser, navigate to <<node_public_ip>>:8080 - to see nginx welcome page

🦉  BONUS LEVEL - Dynamic inventory time!
Create a dynamic inventory out of your current nodes - Add tags to your ec2 node instances and poll them to create your inventory 

🦉  Practice your SSH skills
Create a second playbook that does the following:
1. Creates an ssh keypair locally on the Ansible main node
2. Creates users with your name on the nodes
3. Copies the ssh keypair to the nodes and adds the public key to the authorized_keys file allowing you to connect to it.

Check your work by manually sshing to the nodes with the user you have created.

🦉 Run the playbooks successfully on both ansible nodes, and commit the playbook to you git repo.

Deliverables:
🦉 Link to your git repo with the playbooks
🦉 Screen captures with the successful runs of the playbook on both servers

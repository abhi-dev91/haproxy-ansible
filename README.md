# haproxy-ansible
This repo contains a play to setup HAproxy Load Balancer including Inventory and configuration files
# How to Setup HAproxy(Load Balancer) using Ansible.
Hello Readers, In today's blog I am going to show you How can you setup a Load Balancer (HAproxy) to balance the traffic on webservers.
## For this demonstration, I am using
RHEL 8
Apache httpd
HaProxy
Ansible 2.x

I am showing this practical on my local system. Before starting practical part, Let me tell you what is Load Balancer and Why we need it.
### What is Load Balancer?
A load Balancer is a device or a software which distributes the traffic over multiple webservers running same application, it take the request from client and send the request to webserver, than it took the response from server and responded to the client. This working of Load Balancer is know as reverse proxy, Load Balancer do some more things like inspecting traffic, accepting or rejecting requests etc.
### Why we need Load Balancer?
We need Load Balancer to equally distribute our network traffic to multiple webservers and let our backend servers isolated, With the help of Load Balancer we only have to provide the IP of our Load Balancer to users for accessing our website. This provides us extra security for our instances. There are much more benefits of Load Balancer, but for now let's start implementing it practically.
Setting up load Balancer using Ansible.
## Prerequisite :
SSH connectivity to the instances to be configured, use ssh-copy-id -i ~/.ssh/mykey user@ipaddress
Ansible should be installed on any one node of the computer. To install ansible usepip3 install ansible
git should be installed in the system.
Having root user access or sudo powers.

Lets start setting up HAproxy in our system.
### Step 1: Download the following git repository in ansible node using command
git clone https://www.github.com/pythonBYabhi/haproxy-ansible.git
Cloning repo to local system.
### Step 2: Go to that cloned repo.
cd haproxy-ansible
### Step 3: Open the inventory.txt file and update the IP of the instance on which you want HAproxy to be setup and IP's of your webservers running.
vim haproxy-ansible/inventory.txt
Opening Inventory.txt Fileinventory.txt
### Step 4: After adding IP address run the playbook using command
ansible-playbook haproxy.yml
Running playbookAfter executing the above command it will ask you to choose a port no. on which you want to let your reverse proxy work, Enter the port number and wait for playbook execution.
Playbook ExecutionNow our playbook executed successfully, Now Check the IP of your instance with custom port no. you provided in browser to see weather it is working or not.
Website worked on custom port.That's all folks our Haproxy setup has been completed successfully.
Thanks for reading this blog guys, If u find it useful do clap and share with others too.
If u liked my blog you can also buy me a coffee through - https://ko-fi.com/abhiwritestech

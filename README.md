# CybersecurityProject1
Cybersecurity Elk stack setup
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly reliable, in addition to restricting access to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?
Answer: Load balances protects the availability, Jump box interacts with everything so your indavidual machines dont have to

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.
-TODO: What does Filebeat watch for?_
Answer: Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.
-TODO: What does Metricbeat record?_
Answer:periodically collect metrics from the operating system and from services running on the server. Metricbeat takes the metrics and statistics that it collects and ships them to the output that you specify, such as Elasticsearch or Logstash.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| Web-1    | DVWA     | 10.0.0.6   | Linux            |
| Web-2    | DVWA     | 10.0.0.7   | Linux            |
| Web-3    | DVWA     | 10.0.0.5   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- TODO: 
Answer: My public IP
Machines within the network can only be accessed by my IP
- TODO: Which machine did you allow to access your ELK VM? What was its IP address?_
Answer:Jump Box VM 
13.88.179.42 but it will vary
A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- TODO: What is the main advantage of automating configuration with Ansible?_
Answer: You only have to do it once and it installs and configures on all other boxes

The playbook implements the following tasks:
- TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Answer: 
Install docker
Install pip
Install docker python module
Increase virtual memory
Download and launch docker elk container
- 
The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_
Answer: Configured to moniter Web machines

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_
Answer: filebeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
Answer:They collect data logs from thw web machines and output them into elk so its readable.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the filebeat-playbook.yml file to roles.
- Update the configuration file to include the proper ips
- Run the playbook, and navigate to kibana to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?
Answer: filebeat-playbook.yml - Roles
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
Anwer:Config File - give the correct IP to match the elk
- _Which URL do you navigate to in order to check that the ELK server is running?
Anwer:http://20.57.136.11:5601/app/kibana#/home

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
git clone 
git add .
git commit -m "text"
git push

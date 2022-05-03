# Elk-Stack-Project
These are the scripts that I had created for my first project.
The files in this repository were used to configure the network depicted below.
This document contains the following details:

    Description of the Topology
    Access Policies
    ELK Configuration
        Beats in Use
        Machines Being Monitored
    How to Use the Ansible Build

Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available for customers, in addition to restricting attacks to the network. If a server goes down, or needs to be updated, services will still continue. -The advantage of using a jump box is that only the jump box can access the Virutal network via ssh.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.

    Filebeat monitors the log files or locations specified, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.
    Metricbeat is an extremely easy-to-use, efficient and reliable metric shipper for monitoring your system and the processes running on it.
    Access Policies

The machines on the internal network are not exposed to the public Internet.

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:

    5061 Kibana port

Machines within the network can only be accessed by the Jump-Box-Provisioner.
Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it was easy to do and prevented any easily overloook vulnerablities.

The playbook implements the following tasks:

    Install docker.io
    Install python3-pip
    Install docker via pip
    Increase vitual memory
    Use more memory
    Download and launch a docker elk container - starts docker and establishes the ports being used.

The following screenshot displays the result of running docker ps after successfully configuring the ELK instance.
Target Machines & Beats

This ELK server is configured to monitor the following machines:
-- Web-1 with the ip address of 10.0.0.7
-- Web 2 with the ip address of 10.0.0.8
I have installed Filebeat and Metricbeat on to these machines.
These Beats allow us to collect the following information from each machine: -filebeat collects log data and shows them in the monitoring clusters. -metricbeat collects metrics and statistics and shows them in the output specified, for example Elasticsearch or Logstash.
Using the Playbook

In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:

    Copy the playbook (.yml) file to Ansible directory.
    Update the host file to include webserver and ELK.
    Run the playbook, and navigate to Kibana to check that the installation worked as expected. ( http://[your.VM.IP]:5601/app/kibana )

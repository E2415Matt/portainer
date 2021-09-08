Portainer experiment notes

We have decided to utilise Portainer recently. And I must admit that the experience been a positive one for us.

We have been using DevOps tolls such as Jenkins, Terraform, Cloud Formation, Ansible, Prometheus, Docker, Docker Compose, Kubernetes, etc. however for containerised applications we wanted to try one of the visualisation tools. We have had some experience with Rancher however this time the team decided to experiment with Portainer. I must admit that you cannot have some functionalities you can imagine however simplicity and lightweight nature of the user interface was the convincing part. Portainer CE (Community Edition) is free version and Portainer Business is paid versions. Portainer may not be heavy duty enough for some solutions however we found the free version sufficient for our purpose for the time being.

However, I believe given many alternatives freely available in the market, everyone must make their own decision based on their own needs and experience. Depending on workload and architecture of your solution you may find someone else’s suitable solution useless therefore this article will not advocate or recommend Portainer at all. The aim is to share our experience so far. We believe sharing is caring.

What is Portainer?
Portainer is an open-source lightweight management graphical user interface which allows you to easily manage your Docker environments. Portainer is available on Windows, Linux and Mac. It works with Kubernetes, Docker, Docker Swarm, Azure ACI in both data centres and at the edge as per introduction page of Official website: https://www.portainer.io

Web graphical user interface over default port 9000. Mainly user over GUI, free template library available for some frequently used images. On the other hand, you can also use json based templates. 

Why do I need to use Portainer?
If you are not very familiar with setting up stack you require and if you are after visualising what has been done Portainer is useful. Another reason for using Portainer may well be your wish to manage your containers easier especially if you are not very familiar with command line interface. Portainer makes easier to run environments with multiuser by giving you the ability to assign specific roles to certain uses or groups. In addition, Portainer logs all container management actions so that you can monitor what has been done, when and by whom.


What are pros of Portainer?
-	For the beginners, utilisation of Portainer enables them to start using containerised applications right away. Therefore, reduces the Docker learning curve a lot.
-	Docker developer friendly. Containers just work and you use less time to run them.
-	Operations, documentation, and monitoring gets easier due to simple graphical interface.
-	You can edit the containers and re-deploy them in matter of seconds saving time for those who require quick environment variable changes.
-	Web graphical interface makes monitoring and containers management simpler than cli and takes weight off your mind. 

How to install Portainer?

sudo apt update -y

sudo apt upgrade -y

sudo apt install docker.io

sudo systemctl start docker

sudo systemctl enable docker

sudo apt install docker-compose

sudo docker run -d \
-name=”portainer” \
-restrat on-failure \
-p 9000:9000 \
-v /var/run/docker.sock:/var/run/docker.sock \
-v portainer_data:/data \
portainer/portainer-ce
 
Please go to your internet browser and enter <ip address>:9000 to reach Portainer login interface page. When prompted please ensure to select docker or kubernetes depending on what you are using on that particular machine. Once you entered and confirmed your password the page will take you to Portainer home page. From there you will be able to launch containers, manage endpoints, manage access, use readily available templates, add external templates, manage volumes, manage users, use registries, review logs, monitor stats and more from graphical user interface without needing to use single line of script. Clear graphics and logically laid menu make usage of Portainer much more user friendly comparing docker or kubernetes command line interface.

Final verdict
If you are using containerised applications and need to manage your containers / pods with less time and want to have quick visibility of status of your containers you will probably like using Portainer.

Author:

M. Altun
28Apr2021, London
DevOps Engineer @ Finspire Technology

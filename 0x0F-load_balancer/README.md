## Load Balancer
Ever wonder how Facebook, Linkedin, Twitter and other web giants are handling such huge amounts of traffic? They don’t have just one server, but tens of thousands of them. In order to achieve this, web traffic needs to be distributed to these servers, and that is the role of a load-balancer.

### Readme:
* [Load-balancing](https://www.thegeekstuff.com/2016/01/load-balancer-intro/)
* [Load-balancing algorithms](https://devcentral.f5.com/s/articles/intro-to-load-balancing-for-developers-ndash-the-algorithms)

## Background Context

You have been given 2 additional servers:

* gc-[STUDENT_ID]-web-02-XXXXXXXXXX
* gc-[STUDENT_ID]-lb-01-XXXXXXXXXX

Let’s improve our web stack so that there is [redundancy](https://en.wikipedia.org/wiki/Redundancy_%28engineering%29) for our web servers. This will allow us to be able to accept more traffic by doubling the number of web servers, and to make our infrastructure more reliable. If one web server fails, we will still have a second one to handle requests.

For this project, you will need to write Bash scripts to automate your work. All scripts must be designed to configure a brand new Ubuntu server to match the task requirements.

## Resources:books:
Read or watch:
* [Introduction to load-balancing and HAproxy](https://intranet.hbtn.io/rltoken/ngIXarEyu8jZwOL3Y30PLQ)
* [HTTP header](https://intranet.hbtn.io/rltoken/v32JmcDrSiOnFBfqzXvs_Q)
* [Debian/Ubuntu HAProxy packages](https://intranet.hbtn.io/rltoken/BXGrW_6ocecWaOJb7OK_WA)

---
## Your servers
---
| Name |	Username |	IP |	State |          |        |          |
|------|-----------------|--------- |----------|--------|----------|----|
| 44432-web-01 |	ubuntu |  44.210.108.99 |	running |	Soft reboot |	Hard reboot |	Ask a new server |
| 44432-web-02 |	ubuntu |  44.210.108.99 | 	running |	Soft reboot |	Hard reboot |	Ask a new server |
| 44432-lb-01  |	ubuntu |  44.210.108.99 |	running |	Soft reboot |	Hard reboot |	Ask a new server |
---

### [Task 0. Double the number of webservers](./0-custom_http_response-header)
* In this first task you need to configure web-02 to be identical to web-01. Fortunately, you built a Bash script during your [web server project](https://github.com/mecomonteshbtn/holberton-system_engineering-devops/tree/master/0x0C-web_server), and they’ll now come in handy to easily configure web-02. Remember, always try to automate your work!

Since we’re placing our web servers behind a load balancer for this project, we want to add a custom Nginx response header. The goal here is to be able to track which web server is answering our HTTP requests, to understand and track the way a load balancer works. More in the coming tasks.

Requirements:
* Configure Nginx so that its HTTP response contains a custom header (on web-01 and web-02)
* The name of the custom HTTP header must be X-Served-By
* The value of the custom HTTP header must be the hostname of the server Nginx is running on
* Write 0-custom_http_response-header so that it configures a brand new Ubuntu machine to the requirements asked in this task
* Ignore SC2154 for shellcheck
```
If your server’s hostnames are not properly configured ([STUDENT_ID]-web-01 and [STUDENT_ID]-web-02.), follow this [tutorial](https://aws.amazon.com/premiumsupport/knowledge-center/linux-static-hostname/).

### [Task 1. Install your load balancer](./1-install_load_balancer)
* Install and configure HAproxy on your lb-01 server.

Requirements:
* Configure HAproxy with version equal or greater than 1.5 so that it send traffic to web-01 and web-02
* Distribute requests using a roundrobin algorithm
* Make sure that HAproxy can be managed via an init script
* Make sure that your servers are configured with the right hostnames: [STUDENT_ID]-web-01 and [STUDENT_ID]-web-02. If not, follow this [tutorial](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/set-hostname.html).
* For your answer file, write a Bash script that configures a new Ubuntu machine to respect above requirements
```

### [Task 2. Add a custom HTTP header with Puppet](./2-puppet_custom_http_response-header.pp)
* Just as in task #0, we’d like you to automate the task of creating a custom HTTP header response, but with Puppet.

* The name of the custom HTTP header must be X-Served-By
* The value of the custom HTTP header must be the hostname of the server Nginx is running on
* Write 2-puppet_custom_http_response-header.pp so that it configures a brand new Ubuntu machine to the requirements asked in this task

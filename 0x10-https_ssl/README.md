# HTTPS SSL

In this project, I learned about the importance of HTTPS and how it works. I
configured my HolbertonBnB web servers with `certbot` certificate and HAproxy
SSL termination.

## Resources:books:
Read or watch:
* [What is HTTPS?](https://intranet.hbtn.io/rltoken/pawxG_0c1o86psexBOikIw)
* [What are the 2 main elements that SSL is providing](https://intranet.hbtn.io/rltoken/jXCB9Hn-ALcP78kPMHtnSA)
* [HAProxy SSL termination on Ubuntu16.04](https://intranet.hbtn.io/rltoken/UkbvWfKF6ZAY_CUvlM32lA)
* [SSL termination](https://intranet.hbtn.io/rltoken/VFq2MQ9qHXw2Nb11tnWF6Q)
* [Bash function](https://intranet.hbtn.io/rltoken/v4PUYiN5CxhYKSycYaVvLw)

---
## Learning Objectives:bulb:
What you should learn from this project:

* What is HTTPS SSL 2 main roles
* What is the purpose encrypting traffic
* What SSL termination means
---

## Project Tasks :page_with_curl:

### [Task 0. World wide web](./0-world_wide_web)
* Configure your domain zone so that the subdomain www points to your load-balancer IP (lb-01).
Let’s also add other subdomains to make our life easier, and write a Bash script that will display information about subdomains.
Requirements:
* Add the subdomain www to your domain, point it to your lb-01 IP (your domain name might be configured with default subdomains, feel free to remove them)
* Add the subdomain lb-01 to your domain, point it to your lb-01 IP
* Add the subdomain web-01 to your domain, point it to your web-01 IP
* Add the subdomain web-02 to your domain, point it to your web-02 IP
* Your Bash script must accept 2 arguments:
     domain:
        * type: string
        * what: domain name to audit
        * mandatory: yes
     subdomain:
        * type: string
        * what: specific subdomain to audit
        * mandatory: no
 * Output: The subdomain [SUB_DOMAIN] is a [RECORD_TYPE] record and points to [DESTINATION]
* When only the parameter domain is provided, display information for its subdomains www, lb-01, web-01 and web-02 - in this specific order
* When passing domain and subdomain parameters, display information for the specified subdomain
* Ignore shellcheck case SC2086
   Must use:
   * awk
   * at least one Bash function
   You do not need to handle edge cases such as:
   * Empty parameters
   * Nonexistent domain names
   * Nonexistent subdomains
```

### [Task 1. HAproxy SSL termination](./1-haproxy_ssl_termination)
  Terminating SSL on HAproxy” means that HAproxy is configured to handle encrypted traffic, unencrypt it and pass it on to its destination.

Create a certificate using certbot and configure HAproxy to accept encrypted traffic for your subdomain www..

Requirements:
* HAproxy must be listening on port TCP 443
* HAproxy must be accepting SSL traffic
* HAproxy must serve encrypted traffic that will return the / of your web server
* When querying the root of your domain name, the page returned must contain Holberton School
* Share your HAproxy config as an answer file (/etc/haproxy/haproxy.cfg)

Make sure to install HAproxy 1.5 or higher, SSL termination is not available before v1.5.
```

### [Task 2. No loophole in your website traffic](./100-redirect_http_to_https)
* A good habit is to enforce HTTPS traffic so that no unencrypted traffic is possible. Configure HAproxy to automatically redirect HTTP traffic to HTTPS.
Requirements:
* This should be transparent to the user
* HAproxy should return a 301
* HAproxy should redirect HTTP traffic to HTTPS
* Share your HAproxy config as an answer file (/etc/haproxy/haproxy.cfg)

The file 100-redirect_http_to_https must be your HAproxy configuration file
```

## Author
* **Bello Abayomi A.** - [BluvD143](https://github.com/BluvD143)

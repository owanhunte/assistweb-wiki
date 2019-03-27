<!-- TITLE: Redirecting Ports 80 And 443 -->

At AssistWeb we use *Node.js* for some of our website and applications development. Typically, we put a standard web server such as [Ngninx](https://www.nginx.com) in front of our HTTP Node.js apps. However, on rare occasions, we may choose to run our Node.js app without any actual web server in front of it. By default if we run any of our Node.js apps on port 80 then we have to run them as the root user. To get around this requirement we run them on higher ports such as 8080 (for HTTP) and 3000 (for HTTPS), which allows us to run the app as a non-root user. We then set the following iptable rules:<br><br>

```bash
iptables -t nat -A PREROUTING -i eth0 -p tcp --dport 80 -j REDIRECT --to-port 8080
iptables -t nat -A PREROUTING -i eth0 -p tcp --dport 443 -j REDIRECT --to-port 3000
```
<br>

Note that you may need to run sudo with these commands because they require administrative privileges to run.
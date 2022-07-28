# Ngrok

## Overview

ngrok allows you to expose a web server running on your local machine to the internet.

[Read more about ngrok in the official docs](https://ngrok.com/docs).

## Installation

1. Go to your root directory
```bash
cd
```
2. download ngrok .zip file
```bash
wget https://bin.equinox.io/c/4VmDzA7iaHb/ngrok-stable-linux-amd64.zip
```
if by any chance the url has been changed go to [ngrok download page](https://ngrok.com/download) and copy the url of the linux .zip file.

3. unzip the file
```bash
unzip ngrok-stable-linux-amd64.zip
```
in case you don't have unzip installed, you can do that like this
```bash
sudo apt install unzip
```
4. if you pass in this command `./ngrok` you'll see this output
```
NAME:
   ngrok - tunnel local ports to public URLs and inspect traffic

DESCRIPTION:
    ngrok exposes local networked services behinds NATs and firewalls to the
    public internet over a secure tunnel. Share local websites, build/test
    webhook consumers and self-host personal services.
    Detailed help for each command is available with 'ngrok help <command>'.
    Open http://localhost:4040 for ngrok's web interface to inspect traffic.

EXAMPLES:
    ngrok http 80                    # secure public URL for port 80 web server
    ngrok http -subdomain=baz 8080   # port 8080 available at baz.ngrok.io
    ngrok http foo.dev:80            # tunnel to host:port instead of localhost
    ngrok tcp 22                     # tunnel arbitrary TCP traffic to port 22
    ngrok tls -hostname=foo.com 443  # TLS traffic for foo.com to port 443
    ngrok start foo bar baz          # start tunnels from the configuration file

VERSION:
   2.2.8

AUTHOR:
  inconshreveable - <alan@ngrok.com>

COMMANDS:
   authtoken    save authtoken to configuration file
   credits      prints author and licensing information
   http         start an HTTP tunnel
   start        start tunnels by name from the configuration file
   tcp          start a TCP tunnel
   tls          start a TLS tunnel
   update       update ngrok to the latest version
   version      print the version string
   help         Shows a list of commands or help for one command
```
this means that **ngrok** is working well

5. all you need to do is specify a port where your website is servered so that you expose it to the internet. Example
```
./ngrok http 8000
```
passing the above command will produce this output
```
ngrok by @inconshreveable
Session Expires               7 hours, 59 minutes
Version                       2.2.8
Region                        United States (us)
Web Interface                 http://127.0.0.1:4040
Forwarding                    http://********.ngrok.io -> localhost:8000
Forwarding                    https://*******.ngrok.io -> localhost:8000

Connections                   ttl     opn     rt1     rt5     p50     p90
                              0       0       0.00    0.00    0.00    0.00  
```

6. if you want to run it in the background just run command:Example
```
./ngrok http 80 --log=stdout > ngrok.log &
```

7. if you want create a tunnel just run command:Example
```
./ngrok  http https://yourwebsite.com --log=stdout > ngrok.log &
```
修改端口和部分自用信息

==============

由于原作者并未将改源码部署到Docker.com上，我将源码forked出一份。部署到Docker.com。方便使用。


本人只修改了Dockerfile部分代码，方便部署。

forked from denghongcai/forsaken-mail!!!




Forsaken-Mail
==============
A self-hosted disposable mail service

### Installation

#### Setting up your DNS correctly

In order to receive emails, your smtp server address should be made available somewhere. Two records should be added to your DNS records. Let us pretend that we want to receive emails at ```*@subdomain.domain.com```:
* First an MX record: ```subdomain.domain.com MX 10 mxsubdomain.domain.com```. This means that the mail server for addresses like ```*@subdomain.domain.com``` will be ```mxsubdomain.domain.com```.
* Then an A record: ```mxsubdomain.domain.com A the.ip.address.of.your.mailin.server```. This tells at which ip address the mail server can be found.

You can fire up Mailin (see next section) and use an [smtp server tester](http://mxtoolbox.com/diagnostic.aspx) to verify that everything is correct.

#### Let's Go
general way:
```
npm install && npm start
```
if you want to run this inside a docker container
```

//修改为80端口
docker build github.com/kmm9962/forsaken-mail-80 -t kmm996/forsaken-mail-80
docker run --name forsaken-mail -d -p 25:25 -p 80:80 kmm996/forsaken-mail-80
```
Open your browser and type in
```


http://localhos/
```

Enjoy!

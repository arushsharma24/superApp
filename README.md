# superApp
My super app where I can culminate all the things I know about building apps.

🚀 Starting off with a node js app. 

Documentation:-

 - "https": 
    - Starting an app on http is fine, but for real producion type building, you gotta have https. Now, when I first searched up on how to do this online, I was worried that it was gonna cost money and what not, but then I delved more, found out about this https://letsencrypt.org/ site, which powers making websites https for free. I had tried on another server earlier, but then I didn't really understand nginx, this time I did it right, I followed a [complete tutorial](https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-ubuntu-20-04) and understood things properly, and did it right. Infact, this is the real reason why I decided to make this super app because I was happy that I had finally gotten it to work. But this looks like a promising idea.
 - "pm2":
    - Have to learn how to deploy and do the production/development environment thing with this.
    - Overall this is a pretty neat package tho. Although I wonder how safe using it's env thing is for passing in env secrets and all lol.
    - To save a pm2 configuration, use the `pm2 save` command at the time when the apps you want to be up when restarted are up and running, and also enable pm2 startup by running the `pm2 startup` command.
 - "nginx":
    - How to setup a reverse proxy:- [Youtube video](https://www.youtube.com/watch?v=i8DOV3jNHy4)
    - Description:- Setup a configuration file for your server (you need a domain name for this), put this in name, your_domain(.com or whatever) and www.your_domain.com in the server name. 
    - Also give nginx ufw (firewall permissions)
    - In location, put `proxy_pass http://localhost:$PORT`, this will make it proxy pass. Which is apparently good. Not sure why, learn and update in the future. !TODO
    - Since the proxy_pass will make the node app feel like it is on localhost, to remind it of the real places, add these above location: 
```
  proxy_set_header Host $http_host;
  proxy_set_header X-Real-IP $remote_addr;
  proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
```
  - "more"

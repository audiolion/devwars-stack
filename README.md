# DevWars <img align="right" src="http://i.imgur.com/D9giOVL.png">

*Official Repository to get a local version of [Devwars.tv](http://devwars.tv/)* 

---

### Prerequisites
1. Install [Docker](https://docs.docker.com/install/) and [Docker Compose](https://docs.docker.com/compose/install/)
1. Create a firebase account and put your serviceAccount json in the root directory of the repository with the name `firebase.json`
1. We require an AWS S3 Bucket for storage, so we'll need the following
    * Endpoint URL
    * Access Key
    * Secret Key
    * Bucket Name
1. Create an application in the [Discord Developer Portal](https://discordapp.com/developers/applications/)
1. (Optional) Create a [MailGun](https://www.mailgun.com/) account if you want to send out emails.

### How to get up and running?
1. `git clone --recursive https://github.com/DevWars/devwars-stack.git`
1.  Replace each `.env.service.example` with `.env.service` and fill out each file with the keys we required in the prerequisites
1. Make sure you have a filed called `firebase.json` in the root of the repository. If you run the next step without this, you may see a folder with the name `firebase.json`, if so, just replace it with your real `firebase.json` and restart.
1. `docker-compose up -d`
1. `docker-compose exec api yarn run seed:users`
1. Make sure your [hosts file](https://www.howtogeek.com/howto/27350/beginner-geek-how-to-edit-your-hosts-file/) has the following lines
```text
127.0.0.1 devwars.test
127.0.0.1 www.devwars.test

127.0.0.1 api.devwars.test

127.0.0.1 watch.devwars.test
127.0.0.1 play.devwars.test
``` 

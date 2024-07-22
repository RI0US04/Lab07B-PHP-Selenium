# Steps for pushing into Github:

Please bear in mind this is for Linux env, if windows, I am not too sure hehe

```
git init
git config --global user.name "<insert your github name>"
git config --global user.email "<insert your github email>"
sudo apt-get install dos2unix
dos2unix ./jenkins/scripts/deploy.sh
dos2unix ./jenkins/scripts/kill.sh
```
**Important to stop here, need to fix the deploy.sh**

```
nano deploy.sh
```
Change to 
```
docker run -d -p 80:80 --name my-apache-php-app -v ./src:/var/www/html php:7.2-apache
```
Then continue on:
```
git add jenkins/scripts/deploy.sh
git update-index --chmod=+x jenkins/scripts/deploy.sh
git add jenkins/scripts/kill.sh
git update-index --chmod=+x jenkins/scripts/kill.sh
git commit -m "Add initial files"
git remote add origin <insert your github link> (eg: https://github.com/RI0US04/Lab07B-PHP-Selenium.git)
git branch
git push -u origin master
```
<h3> Reminder that in pushing, use your Github  username and Personal Access Token as password </h3>

## Jenkins Step:
**Ensure that you point to your ip address, even if it is internal ip address (eg: 192.168.220.139) inside the /src/test/java/mycompany/app/AppTest.java**

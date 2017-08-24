## UBUNTU SETUP - FOURTEK

#### Setup and Drive Partition Tutorials
https://www.vembu.com/blog/use-lvm-ubuntu-16-04/

http://www.tutonics.com/2012/11/ubuntu-lvm-guide-part-1.html

https://www.digitalocean.com/community/tutorials/how-to-use-lvm-to-manage-storage-devices-on-ubuntu-16-04

https://askubuntu.com/questions/3596/what-is-lvm-and-what-is-it-used-for

https://www.hiroom2.com/2016/05/19/ubuntu-16-04-extend-and-reduce-lvm-root-filesystem/

https://www.digitalocean.com/community/tutorials/an-introduction-to-lvm-concepts-terminology-and-operations#

https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-16-04


#### After a fresh Ubuntu install


- approve the `report to the...` first popup error

- login to github and go download the dot files folder 

- create workspaces - settings -> appearance-> workspaces


- If the update fails because of **libappstream**
```sh
sudo apt-get purge libappstream3
```

- Install the **libappindicator**


```sh
sudo apt-get install libappindicator1 libindicator7
```




- If the following **apt-update** command fails because of error
```sh
sudo apt-get update
```

Then run this python file

```sh
sudo python3 apt-remove-duplicate-source-entries.py

```


- Brightness controller 

reference 
http://ubuntuhandbook.org/index.php/2017/05/install-brightness-controller-utility-in-ubuntu-16-04-higher/

** Or change the brightness of the monitor manually , buttons

```sh

sudo add-apt-repository ppa:apandada1/brightness-controller
sudo apt-get update
sudo apt-get install brightness-controller
```

- to check system config

```sh
 sudo apt-get install inxi

```


#### Install Ruby 2.3.3

```sh
sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev
```

Then refresh the shell

```sh

exec $SHELL

```

- Install `rbenv`

```sh
cd
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
exec $SHELL


```

- Install `ruby-build`

```sh
git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
exec $SHELL

```

```sh
rbenv install 2.3.3

rbenv global 2.3.3

```

#### LINUXBREW

```sh
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Linuxbrew/install/master/install)"

```

Then add `linuxbrew` to path using these commands

```sh
echo 'export PATH="/home/linuxbrew/.linuxbrew/bin:$PATH"' >>~/.bashrc
echo 'export MANPATH="/home/linuxbrew/.linuxbrew/share/man:$MANPATH"' >>~/.bashrc
echo 'export INFOPATH="/home/linuxbrew/.linuxbrew/share/info:$INFOPATH"' >>~/.bashrc


exec $SHELL

```


#### GIT configuration


Git has already been installed now we only need to configure it.

```sh
git config --global color.ui trueThe next step is to take the newly generated SSH key and add it to your Github account. You want to copy and paste the output of the following command and paste it here.

cat ~/.ssh/id_rsa.pub

Once you've done this, you can check and see if it worked:

ssh -T git@github.com

You should get a message like this:

Hi excid3! You've successfully authenticated, but GitHub does not provide shell access.
git config --global user.name "Abhinav Sharma"
git config --global user.email "abhi18av@gmail.com"
```


- This command will ask for a pass-phrase , don't enter anything - press enter.
```
ssh-keygen -t rsa -b 4096 -C "abhi18av@gmail.com"
```



The next step is to take the newly generated SSH key and add it to your Github account. You want to copy and paste the output of the following command and paste on https://github.com/settings/keys

```
cat ~/.ssh/id_rsa.pub
```
Once you've done this, you can check and see if it worked:

```
ssh -T git@github.com
```

You should get a message like this:

```
Hi excid3! You've successfully authenticated, but GitHub does not provide shell access.
```



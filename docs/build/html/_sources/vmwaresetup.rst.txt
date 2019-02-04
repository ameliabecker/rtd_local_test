VM Setup
========

RTD on "Custom Installs"
------------------------

`local VM Install from RTD: <https://docs.readthedocs.io/en/latest/custom_installs/local_rtd_vm.html>`_


Setting up your login with root access
---------------------------------------

Change to root user:

 `$ su`

 `> (password default configured as root)`


Edit group "wheel":
 | # visudo
 | > ## Allows people in group wheel to run all commands
 | > # % wheel

uncomment “# % wheel”



Add your username to the wheel group:

 `# user mod -aG wheel <username>`

Get subscription manager for RHLE:

 `# subscription-manager with joono.hong-+n@secunetics,com`

 | includes other user passwords


Installing things
------------------

Enable RHEL repos 
 | `# subscription-manager repos --enable "rhel-*-optional-rpms" --enable "rhel-*-extras-rpms"`

To check the available repos:
 | `# yum list all`

install "Wget"
 | # yum install wget

# yum update
  % takes a very long time XP

%%maybe? Test python3 after download
wget https://bootstrap.pypa.io/get-pip.py
python get-pip.py


# On RHEL, enable RHSCL and RHSCL-beta repositories for you system:
$ sudo yum-config-manager --enable rhel-server-rhscl-7-rpms
$ sudo yum-config-manager --enable rhel-server-rhscl-beta-7-rpms

# 2. Install the collection:
$ sudo yum install rh-python36

$scl enable rh-python36 bash

%% test correct libraries:

$ python3 --version
(Python 3.6 or greater)

$ virtualenv —-version
(

%for updating git to 2.18 https://tecadmin.net/install-git-on-centos-fedora/
# yum install curl-devel expat-devel gettext-devel openssl-devel zlib-devel
# yum install gcc perl-ExtUtils-MakeMaker

# cd /usr/src
# wget https://www.kernel.org/pub/software/scm/git/git-2.19.1.tar.gz
# tar xzf git-2.19.1.tar.gz

# cd git-2.19.1
# make prefix=/usr/local/git all
# make prefix=/usr/local/git install

echo "export PATH=/usr/local/git/bin:$PATH" >> /etc/bashrc
source /etc/bashrc

%check with:
# git --version
(Git version 2.19)

$ pip -V
(Pip 9.0)

$ wget http://download.redis.io/releases/redis-5.0.3.tar.gz
$ tar xzf redis-5.0.3.tar.gz
$ cd redis-5.0.3
$ make

# yum install tcl

Nav to redis-5.0.3
# make test

$ sudo yum install python-devel python-pip libxml2-devel libxslt-devel

$ sudo git clone https://github.com/rtfd/readthedocs.org.git
cd readthedocs.org

# pip install --upgrade pip



TBD
---


# sudo pip install Django==1.11.18



Virtualenv??

Pip install -r requirements.txt

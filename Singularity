bootstrap: docker
from:ubuntu:16.04

%label
  MAINTAINER setan
  name pycharm-edu
  APP pycharm
  VERSION 2018.3

%environment
  export PATH=/usr/local/bin:$PATH

%post
  apt-get update -y
  apt-get install -y wget
  apt-get install -y libxext6 libxrender1 libxtst6 libxi6 libfreetype6
  apt-get install -y python3 python3-pip
  apt-get install -y python python-pip
  apt-get clean

  ## CLEANUP
  rm -f pycharm-edu*.tar.gz*
  rm -f /opt/pycharm
  rm -f /usr/local/bin/pycharm
  rm -f /usr/local/bin/inspect
  rm -rf /opt/pycharm-edu-2018.3
  wget https://download.jetbrains.com/python/pycharm-edu-2018.3.tar.gz
  tar zxvf pycharm-edu-2018.3.tar.gz -C /opt
  ln -s /opt/pycharm-edu-2018.3 /opt/pycharm
  ln -s /opt/pycharm/bin/pycharm.sh /usr/local/bin/pycharm
  ln -s /opt/pycharm/bin/inspect.sh /usr/local/bin/inspect
  rm pycharm-edu-2018.3.tar.gz

%runscript
  echo "Run pycharm"
  pycharm

%test
  echo "Done"

%help
This is PyCharm in Ubuntu container.


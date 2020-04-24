# Apache Airflow Configuration

I configured Airflow on windows desktop by enabling the Linux subsystem and dowloading the Ubuntu app from Microsoft store.  
This can also be achived on any kind of Linux flavor running platform( may be slight change in commands)
## Table of Contents

  - [Enable Linux Subsystem](#Enable-Linux-Subsystem)
  - [Download ubuntu from Microsoft store](#Download-ubuntu-from-Microsoft-store)
  - [Prerequisites](#Prerequisites)
  - [Virtual Environment](#Virtual-Environment)
  - [Airflow Installation](#Airflow-Installation)
  - [Creating Airflow home](#Creating-Airflow-home)
  - [Initialize Airflow DB](#Initialize-Airflow-DB)
  - [Start Airflow Scheduler](#Start-Airflow-Scheduler)
  
## Enable Linux Subsystem
### windows > Turn Windows features on or off

![](https://github.com/vijaykothareddy/Data-Engineering/blob/master/Contents/win_feature.PNG)

enable the highlighted feature


## Download ubuntu from Microsoft store

![](https://github.com/vijaykothareddy/Data-Engineering/blob/master/Contents/ubuntu.PNG)

Launching app take you to bash terminal, run below commands


## Prerequisites

update Ubuntu with latest packages

```console
kotharv@vijay-dell:~$ sudo apt-get update
kotharv@vijay-dell:~$ sudo apt-get upgrade
kotharv@vijay-dell:~$ sudo su
```
install `pip` for downloding python modules
`virtualenv` to create a virtualspace for Airflow 

```console
root@vijay-dell:/home/kotharv# apt install python-pip
root@vijay-dell:/home/kotharv# sudo apt install python3-pip
root@vijay-dell:/home/kotharv# apt install virtualenv
```
## Virtual Environment
```console
root@vijay-dell:/home/kotharv# cd /mnt/e/airflow/workspace/
root@vijay-dell:/mnt/e/airflow/workspace# virtualenv -p `which python3` venv
root@vijay-dell:/mnt/e/airflow/workspace# source venv/bin/activate
(venv) root@vijay-dell:/mnt/e/airflow/workspace# 
```

## Airflow Installation
```console
(venv) root@vijay-dell:/mnt/e/airflow/workspace# pip install apache-airflow
```
## Creating Airflow home
```console
(venv) root@vijay-dell:/mnt/e/airflow/workspace# mkdir airflow_home
(venv) root@vijay-dell:/mnt/e/airflow/workspace# export AIRFLOW_HOME=`pwd`/airflow_home
(venv) root@vijay-dell:/mnt/e/airflow/workspace# echo $AIRFLOW_HOME
/mnt/e/airflow/workspace/airflow_home
(venv) root@vijay-dell:/mnt/e/airflow/workspace# airflow version
1.10.10
(venv) root@vijay-dell:/mnt/e/airflow/workspace# cd airflow_home/
(venv) root@vijay-dell:/mnt/e/airflow/workspace/airflow_home# ls
airflow.cfg  logs  unittests.cfg
```
## Initialize Airflow DB
```console
(venv) root@vijay-dell:/mnt/e/airflow/workspace# airflow initdb
Start Airflow Webserver
(venv) root@vijay-dell:/mnt/e/airflow/workspace# airflow webserver
```
## Start Airflow Scheduler
```console
(venv) root@vijay-dell:/mnt/e/airflow/workspace# airflow scheduler
```
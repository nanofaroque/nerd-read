# Apache Airflow

### Install, up and running
* http://michal.karzynski.pl/blog/2017/03/19/developing-workflows-with-apache-airflow/

conda create --name airflow python=3.6
conda activate airflow
mkdir airflow
cd airflow
mkdir workspace
cd workspace
mkdir airflow_home


export AIRFLOW_HOME=`pwd`/airflow_home
airflow version

## now check the airflow_home directory and see the configs and dags file
airflow initdb

## Now start the server
airflow webserver

## you have to start the scheduler to see the new DAG
airflow scheduler

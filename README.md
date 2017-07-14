### oic-add-user

This post show how to add new data analyst user in oic-projet. Data analyst should have access to to following services:
- HDFS
- HUE
- Jupyter

> HDFS `Client Node [hadoop-w-3]`  

```sh  
# Create user
sudo adduser user_test 
sudo passwd user_test # set password

# Log as hadoop superuser
sudo su - hdfs

# Create user home directory in HDFS
hadoop fs –mkdir /user/user_test/

# Change the ownership of user home directory in HDFS
hadoop fs –chown –R user_test:user_test /user/user_test

# Change ACL of user folder
hadoop fs -chmod -R 750 /user/user_test

```  

> HUE: go to HUE Web UI and add user manually

> Jupyter `Client Node [hadoop-w-3]`  

```sh  
# Edit /home/agambo/jupyterhub_config.py file
sudo nano /home/agambo/jupyterhub_config.py

# add user name in c.Authenticator.whitelist 

```

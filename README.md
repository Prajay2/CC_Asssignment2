## Steps:
1) ssh into 4 instances
2) use the following and repeat the steps for all 4:
ssh-keygen -t rsa-N “”-f /home/ubuntu/.ssh/id_rsa
Cd .ssh
ls-lrt
 →to get all the public keys from everywhere use the below command,
cat ~/.ssh/id_rsa.pub

3) vim authorized_keys (copy paste all 4 keys in all 4 instances)

4) cd
sudo vim /etc/hosts
<ip-address> nn
<ip-address> dd1
...
..           dd3

5) Install java, maven, spark-3.4.1

workers.template is inside : $SPARK_HOME/conf/workers

6) Do : cp workers.template workers

7) Then vim  in workers -->
 put the below after localhost
dd1/ip-address
dd2/ip-address
dd3/ip-address



 

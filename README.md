## Cluster Creation AWS SPARK:
 1.	GO to the EMR console and then click on create new instance.
 2. Name  your cluster.
 3.	In cluster Termination, change to manual from automatic.
 4.	Provide the key_pair which is a .pem file in security configuration
 
 5.	In instance creation, provide 1 for core and 4 for tasks as we need to run on 4 EC2 instances.
 6.	Then select default roles for the IAM roles.
 
 7.	Create a S3 queue to upload the python and csv files.
 s3://wineprecdit
 
 8.	Open terminal and use the below command to connect to the cluster.
 ssh -i ~/newproject2.pem hadoop@ec2-52-201-250-228.compute-1.amazonaws.com

## Execution without Docker
 1. Run “sudo su” command to change user.
 2. Install numpy by using ‘pip install numpy --user’
 3. Then run “spark-submit s3://wineprecdit/training.py”. It runs the file from S3 bucket and creates a ML model
 4. Then run “spark-submit s3://wineprecdit/prediction.py s3://wineprecdit/ValidationDataset.csv”. It uses the model created and validates the data from the csv file and provides the result. 




 

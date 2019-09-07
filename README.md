# Python_list_ec2
## Python - This is a python code to list all instances from a region.

```python
import boto3
ec2=boto3.resource("ec2",region_name="us-east-2")
for instance in ec2.instances.all():
     print(
         "Id: {0}\nPlatform: {1}\nType: {2}\nPublic IPv4: {3}\nAMI: {4}\nState: {5}\n".format(
         instance.id, instance.platform, instance.instance_type, instance.public_ip_address, instance.image.id, instance.state
         )
     )
```

### The output of the above code will look like as follows.

```
Id: i-0a70d15b4fe******
Platform: None
Type: t2.micro
Public IPv4: None
AMI: ami-0d8f6eb4f641ef691
State: {'Code': 80, 'Name': 'stopped'}

Id: i-0eb4a34fee0******
Platform: None
Type: t2.micro
Public IPv4: 18.219.165.162
AMI: ami-05c1fa8df71875112
State: {'Code': 16, 'Name': 'running'}

Id: i-0124fcbad42******
Platform: None
Type: t2.micro
Public IPv4: None
AMI: ami-0d8f6eb4f641ef691
State: {'Code': 80, 'Name': 'stopped'}
```

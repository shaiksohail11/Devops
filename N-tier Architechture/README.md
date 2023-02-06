Create VPC for N-tier Architechture
------------------------------------

* Create a VPC with 6 Subnets
* 3 subnets in one  AZ (web1,app1,db1) 
* 3 subnets in another AZ (web2,app2,db2)

![Preview](../../Images/vpc1.png)

* Create a VPC
![Preview](../../Images/vpc2.png)

* Create 6 subnets
* filter the subnets with the `vpc id` in filter options.
![Preview](../../Images/vpc3.png)

* In this vpc we have a default route table
* All the internal communications with in vpc is allowed
![Preview](../../Images/vpc4.png)

* With every vpc created we get a default security group
![Preview](../../Images/vpc5.png)

* network acl
![Preview](../../Images/vpc6.png)

* Lets create an ec2 instance in web1 subnet
![Preview](../../Images/vpc7.png)

* Now select the Vpc you have created 
* Select the subnet
* Enable Public Ip
![Preview](../../Images/vpc8.png)
![Preview](../../Images/vpc9.png)

* Now to connect to this instance from outside let us use
```
ssh -i <path to pem> ubuntu@<public-ip>
```
![Preview](../../Images/vpc10.png)

* This will not work as we do not have internet connectivity
![Preview](../../Images/vpc11.png)

* Lets create internet gateway and attach this to vpc
![Preview](../../Images/vpc12.png)
![Preview](../../Images/vpc13.png)
![Preview](../../Images/vpc14.png)
* Select your vpc and create internet gataway

![Preview](../../Images/vpc15.png)

* Now enable route between route table and internet gateway.
* Navigate to route table then routes
![Preview](../../Images/vpc16.png)
![Preview](../../Images/vpc17.png)
![Preview](../../Images/vpc18.png)
* Lets try to connect ssh from laptop again
![Preview](../../Images/vpc19.png)
![Preview](../../Images/vpc20.png)
![Preview](../../Images/vpc21.png)
* Lets look at network interface which is called as elastic network interface by aws
![Preview](../../Images/vpc22.png)
* Security Group is attached to network interface which allows only the packets with entries written in security group
![Preview](../../Images/vpc23.png)

Mind map to create Aws own vpc
------------------------------
![Preview](../../Images/vpc24.png)



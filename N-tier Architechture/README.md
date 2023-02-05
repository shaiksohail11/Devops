Create VPC for N-tier Architechture
------------------------------------

* Create a VPC with 6 Subnets
* 3 subnets in one  AZ (web1,app1,db1) 
* 3 subnets in another AZ (web2,app2,db2)

![Preview](../../images/vpc1.png)

* Create a VPC
![Preview](../../images/vpc2.png)

* Create 6 subnets
** filter the subnets with the `vpc id` in filter options.
![Preview](../../images/vpc3.png)

* In this vpc we have a default route table
* All the internal communications with in vpc is allowed
![Preview](../../images/vpc4.png)

* With every vpc created we get a default security group
![Preview](../../images/vpc5.png)

* network acl
![Preview](../../images/vpc6.png)

* Lets create an ec2 instance in web1 subnet
![Preview](../../images/vpc7.png)

* Now select the Vpc you have created 
* Select the subnet
* Enable Public Ip
![Preview](../../images/vpc8.png)
![Preview](../../images/vpc9.png)

* Now to connect to this instance from outside let us use
```
ssh -i <path to pem> ubuntu@<public-ip>
```
![Preview](../../images/vpc10.png)

* This will not work as we do not have internet connectivity
![Preview](../../images/vpc11.png)

* Lets create internet gateway and attach this to vpc
![Preview](../../images/vpc12.png)
![Preview](../../images/vpc13.png)
![Preview](../../images/vpc14.png)
* Select your vpc and create internet gataway

![Preview](../../images/vpc15.png)

* Now enable route between route table and internet gateway.
* Navigate to route table then routes
![Preview](../../images/vpc16.png)
![Preview](../../images/vpc17.png)
![Preview](../../images/vpc18.png)
* Lets try to connect ssh from laptop again
![Preview](../../images/vpc19.png)
![Preview](../../images/vpc20.png)
![Preview](../../images/vpc21.png)
* Lets look at network interface which is called as elastic network interface by aws
![Preview](../../images/vpc22.png)
* Security Group is attached to network interface which allows only the packets with entries written in security group
![Preview](../../images/vpc23.png)

Mind map to create Aws own vpc
------------------------------
![Preview](../../images/vpc24.png)



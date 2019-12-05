# industrial-manufacturing

Launch one of the following CloudFormation templates per your region of choice (suggest Oregon), to deploy resources for the session.

  * [Oregon](https://us-west-2.console.aws.amazon.com/cloudformation/home?region=us-west-2#/stacks/create/review?templateURL=https://s3-us-west-2.amazonaws.com/industrial-architecture-workshop-us-west-2/2019-06-04/cfn-iiot-workshop.json&stackName=IIoTWS)
  * [Ireland](https://eu-west-1.console.aws.amazon.com/cloudformation/home?region=eu-west-1#/stacks/create/review?templateURL=https://s3-eu-west-1.amazonaws.com/industrial-architecture-workshop-eu-west-1/2019-06-04/cfn-iiot-workshop.json&stackName=IIoTWS)
  * [N. Virginia](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create/review?templateURL=https://s3.amazonaws.com/industrial-architecture-workshop-us-east-1/2019-06-04/cfn-iiot-workshop.json&stackName=IIoTWS)
  
## Greengrass install commands

sudo tar -xzvf ~/environment/my-greengrass/greengrass-linux-x86-*.tar.gz -C /

sudo tar -xzvf ~/environment/my-greengrass/*-setup.tar.gz -C /greengrass

* Using yum install Java 8.

sudo yum install java-1.8.0-openjdk

* Switch /usr/bin/java to link to the java8 version.

sudo ln -sf /usr/bin/java8 /usr/bin/java

* Start Greengrass with the following command

sudo /greengrass/ggc/core/greengrassd start


Note: If the deploy fails run the following commands  in the terminal window.

gg_service_arn=$(aws iam get-role --role-name Greengrass_ServiceRole --query Role.Arn)

aws greengrass associate-service-role-to-account —role-arn ${gg_service_arn//\"/}


{   
    name: 'Drill.DrillState',
    nodeId: 'ns=5;s=MAIN.Drill.DrillState',
},
{   
    name: 'Drill.Pressure',
    nodeId: 'ns=5;s=MAIN.Drill.Pressure',
},
{   
    name: 'Drill.SpindleSpeed',
    nodeId: 'ns=5;s=MAIN.Drill.SpindleSpeed',
},
{   
    name: 'Drill.MotorSpeed',
    nodeId: 'ns=5;s=MAIN.Drill.MotorSpeed',
}



# Manufacturing Reference Architecture

[Manufacturing Reference Architecture](https://awsreferencearchitecture.com/manufacturing/)

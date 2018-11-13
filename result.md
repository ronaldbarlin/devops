In this project, I am using AWS to finish it.
# set up
1. in this case, I am using EC2 virtual machine. 
1. Chose the region to be singapore
1. click "Launch Instance" then I chose Ubuntu server 16 as the AMI
1. Choose the instance type basen on the need of vCPU and the size of memory
1. Then we can fill all the data needed in the Configure Instance details, next we add Storage, then configure security group
1. We can Review our machine before we launch it.
# connect the instance
1. we can use a puttyGen to connect the instance using the data provided when you click the "connect" button for your instance in AWS
1. now our machine is ready. we can terminate it whenever needed by click the actions-instance state- terminate
# upload the project to the instance and create the scalling
1. we upload our project to the EC2 machine using the help of filezilla to transfer data.
1. after we upload the project, we create the Image of the project. click actions-image-create image. fill the data for the image such as name, description, etc then click create image.
1. now we back to the auto scalling then create the launch configuration. we fill all the data needed, similar to the one when we create the instance. it will show a messages when success to create it.
1. create  auto scalling group. also fill all the data needed. the details will be on next topic.
# autoscalling
1. fill the group name, etc. click next
1. configure the scalling policies to add and remove instance. we can do this based on cpu utilization, network in. network out, etc. for example
    - scale between someting to something instances. for example 2 to 5 instances.
    - we add a new instance when the CPU utilization is >= 70% for consecutive 60 seconds to make the instance work more lightly.
    - we can also remove one instance when the CPU utilization is <= 30% to reduce costs.
1. fill the data needed in configure notification and configure tags, then review and finally click the create autp scalling group.
1. a success message will shown.
# finally
at this points, our website should be running well. we can use the IP address provided in the AMI to open the website(what customers view).
when the CPU utilization is high, means a lot of people using our service. it will automatically open a new instance to keep everything runs smoothly. 
in reverse, after the cpu utilization is low, which means many people are not using the service at the time anymore, 1 or more instance will be closed, but not all because the main instance will remain running.

# Demo create server EC2

In this tutorial, I will create simple and practical example of how to provision EC2 instance with Github Actions and Terraform. I will use workflow_dispatch type of workflow which is triggered manually by user, using Terraform Github action from HashiCorp.

## Goal
Deploy EC2 instance of t3.small size to your AWS account using Github Actions and Terraform.

I will use ‘workflow_dispatch’ event for this, which is manually triggered.
### workflow_dispatch
> This event occurs when someone triggers a workflow run on GitHub or sends a POST request to the "Create a workflow dispatch event" endpoint. For more information, see "Events that trigger workflows."

### Dependencies 
ADD secrets github
**AWS user key**
**AWS user secret**

### Overview of terraform script to provision EC2 instance

-   The provisioned instance based on ubuntu AMI.
-   Instance type selected by default is t3.micro.
-   Instance will be provisioned to default VPC | subnet | security group.
-   Need to create SSH key pair to connect with provisioned instance.
-   EC2 will be provisioned select by default ‘us-east-1’ region.

## Try to connect

Now try to connect to this instance using ‘ssh-key’ 

I downloaded ssh-key.pem file

```
chmod 600 ssh-key.pem
ssh -i ssh-key.pem ubuntu@<IP Public>
uname -a
```

Success!

##### Credits
> [https://github.com/warolv/github-actions-series.git‘](https://github.com/warolv/github-actions-series.git)(@warolv)

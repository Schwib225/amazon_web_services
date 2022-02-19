# Identity and Access Management

Users and Groups

# Very straight forward if you've ever made users or groups before - permissions policies can be applied and inherited - not going into detail about that here for now

Users can be apart of multiple groups, groups can only contain users

# Setting Up MFA - Through the security settings for the user - pretty straight forward

# Setting up the AWS Cli 
(Download most recent version then execute the following)

  aws configure
  # Generated access key and secret from aws web console (Under the user > security settings > Access keys)
  Access key: asdfl;kjasdfl;kj
  Secret: adl;kjasdflk
  region: aws-west-2
  output format [None]:
  
  
# AWS CloudShell - alternative to the AWS Cli and you want a terminal (not available in every region)

Plus side of cloudshell you can create scripts and files and they will be persistent under your account/instance - basically a linux terminal via the web

# Some Generic Commands for cli 

  aws iam help            # This will list all the sub-commands for IAM - there are quite a few, you can reset passwords, create users/groups/etc from here 
  
  aws iam list-users      # this will list all users in the environment if the user has access to this info
  
# IAM Roles

Intended to be used by an aws service, not a user 

  IAM > Roles > Create Role > 'Select entity' (ec2 instsance) > "Add permissions" (adding awsreadonly for example) 
  
  
# IAM Security Tools

IAM Credential Report (Account level)
  Lists all accounts users and the status 
  
  IAM > Access Reports > Credential Report (downloads a csv file)
  
IAM Access Advisor (User Level)
  Lists all permissions to a user and when the service was last accessed - used to revise permissions
  
  IAM >  Users > Select User > Access Advisor (tab) - you will see all activity for the user
  
# Best Practices

1. Don't use the root acct except for AWS acct setup
2. One physical user = one aws user
3. Assign users to groups and assign permissions to groups
4. Create a strong password policy
5. Use and enforce MFA 
6. Create and use Roles for giving permissions to aws services
7. Use access keys for programmatic access 
8. Audit permissions of your acct with iam credentials report 
  

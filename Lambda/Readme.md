AWS Cloud Cost Optimization - Identifying Stale Resources
Identifying Stale EBS Snapshots
In this example, we'll create a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.

Description:
The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.

STEPS:
The goal is for lambda function to delete any Snapshot attached to a volume that is not attached to any EC2 instance.
We will try various cases to execute lambda function when a Snapshot is attached to an ec2 instance
We will also try to execute the lambda function when the ec2 instance is deleted and observe the results on both cases:
Create ec2 name it appropriately with a default volume.
Take a Snapshot of the volume.
Go to lambda function and create lambda function name it appropriately.
Choose python from the programming language.
Go to GitHub page and copy the python script written by the developer.
Paste the python code on the code field of lambda function and save.
Name the lambda function appropriately.
Go to configuration tab on the lambda function.
Increase the default execution Timeout of 3 seconds to 10 seconds and save.
GRANT PERMISIONS, CREATE ROLES, POLICIES
Go to configuration , click on Permission, Click on Role name link
Click on the Add Permission dropdown
Click on create policies
Choose ec2 from list of services
Type snapshot in the search bar
Choose two options: Describe Snapshots, Delete Snapshots, click Next
Click next, Name the policy appropriately and create policy
Create another policy
Choose ec2 from services
Choose List from the options
Choose 2 options: Describe volumes, Describe instances.
Click on Next button and Name policy appropriately and create policy
Go back to the role and attach the two policies created Click next
Go to the Lambda page and execute manually and see result

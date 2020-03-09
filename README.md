# ib2aws
# AMI Creation

THE PLAYBOOKES USED IN THIS ARE BEING RUN LOCALLY 

1. Subscribe machine 
2. Add ansible repo to yum 
3. Install ansible
4. Run 'ansible-playbook install-cockpit-and-IB.yml' 
5. Run 'ansible-playbook image-creation.yml'
There you have a custom built AMI!

# Upload to AWS

THE PLAYBOOKES USED IN THIS ARE BEING RUN LOCALLY 

6. Run 'ansible-playbook install-aws-cli.yml'
7. Configure host to connect to AWS using 'aws configure'
8. Store aws aws_access_key and aws_secret_key in a file called anisible vault file called 'secrets.yml' to do so run the command 'ansible-vault create secrets.yml' make sure to save a secure password after editing the yml file for an example look at 'example-secret.yml' 
9. Run 'ansible-playbook push-to-aws.yml --extra-vars @secrets.yml --ask-vault-pass' 
10. Check S3 Bucket to see new image in bucket
11. Check EBS snapshots for new image snaphot 
12. Right click on the new snapshot to create image

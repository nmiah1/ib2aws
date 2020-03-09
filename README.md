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
8. Store aws aws_access_key and aws_secret_key in a file called 'secrets.yml' for an example look at 'example-secret.yml' 
8. Run 'ansible-playbook push-to-aws.yml --extra-vars @secrets.yml --ask-vault-pass' 
9. Check S3 Bucket to see new image in bucket
10. Check EBS snapshots for new image snaphot 
11. Right click on the new snapshot to create image

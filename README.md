# Ansible-task

Please see the playbooks 

the Master play co-ordinates every and is the actual play that runs the other sub playbooks in the order of-

Backup_playbook ( yours to take the sql dump)
S3_sync_playbook ( to copy the file into S3, apparently there is a module for S3)
Delete_playbook ( to delete the .sql.gz file from the rds server)
SNS_playbook ( to send sns email notification of successful backup)  

i haven’t figured out how to do the sms notification in case of failure though, but please let me know how we can include the brownie items you mentioned on the chat in any of the playbooks

also my assumptions are -
i  assume that both 3 ( aws python library to secure connection btw Rds<<>>S3) is installed
Assume SNS Topic configured and setup with S3 ARN included as well as email endpoint subscribed
Assume necessary IAM policies in place for RDS server to access S3
bucket created in S3


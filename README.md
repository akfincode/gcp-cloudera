## Cloudera on Google Cloud

Portal for detailed steps to install CDH 5 on Google Cloud and custom application integration.

## Installation

Spin up multiple GCP compute instances (Nodes). Verify all prices / charges.

SSH into each node and execute the following:

vi /etc/ssh/sshd_config

PermitRootLogin yes
PubkeyAuthentication yes
AuthorizedKeysFile /.ssh/authorized_keys
ChallengeResponseAuthentication yes

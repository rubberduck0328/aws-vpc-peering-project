# AWS VPC Peering Project

EWB Cloud Labs / AWS internship project. Two private VPCs connected with VPC peering, with a bastion host for SSH administration.

- Region: Asia Pacific (Sydney), ap-southeast-2
- VPC A: 10.10.0.0/16 (public subnet 10.10.1.0/24, private subnet 10.10.2.0/24)
- VPC B: 10.20.0.0/16 (private subnet 10.20.1.0/24)
- Peering connection: pcx-0efb9f1bce8e2f46e (Active)
- Instances: Bastion (10.10.1.76), App-A (10.10.2.10), App-B (10.20.1.10), Amazon Linux 2023, t3.micro

## What was demonstrated
- Non-overlapping VPC CIDRs, public and private subnets, three custom route tables
- Routes on both sides of the peering connection
- Least-privilege security groups (/32 sources, no 0.0.0.0/0)
- SSH to private instances through the bastion
- Two-way ping between App-A and App-B
- Controlled failure (ICMP rule removed, 100% packet loss) and recovery (rule restored)

## Contents
- `documentation/`: full project report (PDF)
- `diagrams/`: architecture diagram
- `screenshots/`: route tables, peering, security groups and test evidence

## Notes
No baseline test before peering was captured, and cleanup was not completed at the time of submission (AWS console unresponsive).
No private keys are included in this repository.

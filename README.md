# GCP-secure-vpc-bastion-nat
I built a custom VPC in GCP with public and private subnets. The bastion host is the only public entry point, and firewall rules restrict SSH access using network tags. Private instances have no public IPs and access the internet through Cloud NAT. I validated secure access using SSH agent forwarding without storing keys on the bastion

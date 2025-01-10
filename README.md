# WordPress Deployment on AWS Cloud Infrastructure

## Project Overview
This project demonstrates the deployment of a highly available, scalable WordPress website on AWS using various cloud services and best practices. The architecture spans multiple availability zones with both public and private subnets, ensuring robust security and fault tolerance.

## Architecture Components

### Networking
- **VPC Configuration**: Custom VPC with public and private subnets across two availability zones
- **Internet Gateway**: Enables communication between VPC instances and the internet
- **NAT Gateway**: Allows private subnet instances to access the internet
- **EC2 Instance Connect Endpoint**: Secure connection to resources in both public and private subnets

### Security
- **Security Groups**: Network firewall controlling inbound and outbound traffic
- **Private Subnets**: Hosting web servers for enhanced security
- **Certificate Manager**: Securing application communications
- **IAM Roles**: Managing permissions and access control

### Compute and Storage
- **EC2 Instances**: Web servers running in private subnets
- **Auto Scaling Group**: Automatically manages EC2 instances across availability zones
- **Elastic File System (EFS)**: Shared storage for application code
- **RDS**: Managed relational database in private data subnet

### Load Balancing and DNS
- **Application Load Balancer**: Distributes traffic across EC2 instances
- **Route 53**: DNS management and domain registration

### Monitoring and Notifications
- **SNS**: Alerts for Auto Scaling Group activities

### Version Control
- **GitHub**: Storage and version control for web files

## Deployment Script
The project includes a bash script for deploying WordPress and its dependencies on EFS. The script handles:
- System updates
- Apache web server installation
- PHP 8 installation with required extensions
- MySQL 8 community server setup
- EFS mounting and permissions configuration

## Prerequisites
- AWS Account with appropriate permissions
- Registered domain name
- GitHub account
- Basic understanding of AWS services

## Security Considerations
- Web servers are placed in private subnets
- Database tier is isolated in private data subnet
- Security groups implement principle of least privilege
- SSL/TLS certificates secure communications
- EC2 Instance Connect Endpoint for secure instance access

## High Availability Features
- Multi-AZ deployment
- Auto Scaling Group for EC2 instances
- Load balancer for traffic distribution
- RDS in private subnet
- EFS for shared storage

## Monitoring and Maintenance
- SNS notifications for Auto Scaling events
- CloudWatch metrics and alarms
- Regular backup procedures
- Version control for application code

## Future Enhancements
- Implement caching layer using ElastiCache
- Set up CI/CD pipeline
- Add WAF for enhanced security
- Implement disaster recovery procedures
- Configure automated backups

## Getting Started
1. Clone the repository
2. Configure AWS credentials
3. Deploy VPC and networking components
4. Set up EFS and RDS instances
5. Deploy EC2 instances with the provided script
6. Configure load balancer and auto scaling
7. Set up DNS and SSL certificates
8. Test the deployment

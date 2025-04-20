
# Netdata Monitor Setup on EC2

## Simple Steps:

1. Launch EC2 (Amazon Linux 2, t2.micro)
2. Open port 19999 in Security Group
3. Connect to EC2 via SSH
4. Run these commands:

```bash
sudo yum update -y
sudo yum install docker -y
sudo service docker start
sudo systemctl enable docker
sudo docker run -d --name=netdata -p 19999:19999 --cap-add SYS_PTRACE --security-opt apparmor=unconfined netdata/netdata

Open in browser:
http://<EC2_PUBLIC_IP>:19999

Optional: Check logs

#base
apt update && apt upgrade -y && apt-get install qemu-guest-agent -y && apt-get install xfce4 -y && apt-get install xrdp -y && apt install net-tools -y && systemctl start qemu-guest-agent && systemctl enable qemu-guest-agent && systemctl stop ufw && systemctl disable ufw && apt update && apt upgrade -y

#git+docker
apt install git -y && apt install docker -y && apt install docker-compose -y

#partainer
docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest

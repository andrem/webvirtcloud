## WebVirtCloud

### Description

WebVirtMgr is a libvirt-based Web interface for managing virtual machines for admins and users. It allows you to create and configure new domains, and adjust a domain's resource allocation. A noVNC viewer presents a full graphical console to the guest domain.  KVM is currently the only hypervisor supported. 

### Install WebVirtCloud panel

```bash
sudo apt-get -y install git python-pip python-dev python-libvirt python-libxml2 nginx supervisor
git clone https://github.com/retspen/webvirtcloud
cd webvirtmgr
sudo pip install -r conf/requirements.txt
python manage.py migrate
sudo cp conf/supervisor/webvirtcloud.conf /etc/supervisor/conf.d
sudo cp conf/nginx/webvirtcloud.conf /etc/nginx/conf.d
cd ..
sudo mv webvirtcloud /var/www/
sudo chown -R www-data:www-data /var/www/webvirtcloud
```

Restart services for running WebVirtCloud:

```bash
sudo service nginx restart
sudo service supervisor restart
```

### Setup hypervisor

```bash
wget -O - https://clck.ru/9Sz6S | sudo sh
```

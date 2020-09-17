# nowIT VPN: enterprise vpn server

### ubuntu xenial - DigitalOcean User Data

```bash
#!/bin/bash

sudo tee /etc/apt/sources.list.d/mongodb-org-4.2.list << EOF
deb https://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/4.2 multiverse
EOF

sudo tee /etc/apt/sources.list.d/pritunl.list << EOF
deb https://repo.pritunl.com/stable/apt xenial main
EOF

sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com --recv E162F504A20CDF15827F718D4B7C549A058F8B6B
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com --recv 7568D9BB55FF9E5287D586017AE645C0CF8E292A
sudo apt-get --assume-yes install apt-transport-https
sudo apt-get update
sudo apt-get --assume-yes install pritunl mongodb-org git
git clone https://github.com/rodolphoescobar/nowit-vpn.git
cp -avr ./nowit-vpn/ /usr/share/pritunl/www
rm -rf nowit-vpn
sudo systemctl start pritunl mongod
sudo systemctl enable pritunl mongod
```

### ubuntu bionic - DigitalOcean User Data

```bash
#!/bin/bash

sudo tee /etc/apt/sources.list.d/mongodb-org-4.2.list << EOF
deb https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.2 multiverse
EOF

sudo tee /etc/apt/sources.list.d/pritunl.list << EOF
deb https://repo.pritunl.com/stable/apt bionic main
EOF

sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com --recv E162F504A20CDF15827F718D4B7C549A058F8B6B
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com --recv 7568D9BB55FF9E5287D586017AE645C0CF8E292A
sudo apt-get update
sudo apt-get --assume-yes install pritunl mongodb-server git
git clone https://github.com/rodolphoescobar/nowit-vpn.git
cp -avr ./nowit-vpn/ /usr/share/pritunl/www
rm -rf nowit-vpn
sudo systemctl start pritunl mongodb
sudo systemctl enable pritunl mongodb
```

### ubuntu focal - DigitalOcean User Data

```bash
#!/bin/bash

sudo tee /etc/apt/sources.list.d/mongodb-org-4.2.list << EOF
deb https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/4.2 multiverse
EOF

sudo tee /etc/apt/sources.list.d/pritunl.list << EOF
deb https://repo.pritunl.com/stable/apt focal main
EOF

sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com --recv E162F504A20CDF15827F718D4B7C549A058F8B6B
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com --recv 7568D9BB55FF9E5287D586017AE645C0CF8E292A
sudo apt-get update
sudo apt-get --assume-yes install pritunl mongodb-server git
git clone https://github.com/rodolphoescobar/nowit-vpn.git
cp -avr ./nowit-vpn/ /usr/share/pritunl/www
rm -rf nowit-vpn
sudo systemctl start pritunl mongodb
sudo systemctl enable pritunl mongodb
```

## License

Please refer to the [`LICENSE`](LICENSE) file for a copy of the license.

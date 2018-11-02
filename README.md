### Installation

#### Setup the server
```
$ git clone git@github.com:mike-bhs/docker-sftp.git
$ cd docker-sftp
$ docker-compose up -d
```

#### SSH user login
```
$ ssh master@localhost -p 2222
# password: master

# or you can login as root to container instead
$ docker-compose exec server bash
```

#### Add a new SFTP user
```
$ sudo mkdir /uploads/sftp_sandbox
$ sudo mkdir /uploads/sftp_sandbox/upload
$ sudo useradd -d /uploads/sftp_sandbox -G sftp sftp_sandbox -s /usr/sbin/nologin
$ echo "sftp_sandbox:sftp_sandbox" | sudo chpasswd
$ sudo chown sftp_sandbox:sftp -R /uploads/sftp_sandbox/upload
```

#### SFTP user login
```
$ sftp -P 2222 sftp_sandbox@localhost
# password: sftp_sandbox
```

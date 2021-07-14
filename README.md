# scripts-go-release

Create a golang program that prints "hello world" in a Vagrant box. We'll also use travis-ci hosted service to :
 - Test the built program prints hello world successfully (CI)
 - Upload the hello file into GitHub release after tag creation (CD)

### Pre-requirements

* [Vagrant](https://www.vagrantup.com/downloads)
* [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
* [travis-ci account](https://travis-ci.com)

### How to use this repo

- Clone
- Build
- Create a TAG
- Check deployment

---

### Clone the repository

```
git clone https://github.com/viv-garot/scripts-go-travis
```

### Change directory

```
cd scripts-go-travis
```

### Build the Box

```
vagrant up
```

### Sample output

```
vagrant up
Bringing machine 'default' up with 'virtualbox' provider...
==> default: Importing base box 'vivien/bionic64'...
==> default: Matching MAC address for NAT networking...
==> default: Checking if box 'vivien/bionic64' version '21.07.06' is up to date...
==> default: Setting the name of the VM: scripts-go_default_1626183188856_46312
==> default: Clearing any previously set network interfaces...
==> default: Preparing network interfaces based on configuration...
    default: Adapter 1: nat
==> default: Forwarding ports...
    default: 22 (guest) => 2222 (host) (adapter 1)
==> default: Booting VM...
==> default: Waiting for machine to boot. This may take a few minutes...
    default: SSH address: 127.0.0.1:2222
    default: SSH username: vagrant
    default: SSH auth method: private key
    
[...]

    default: 2021-07-13 13:34:17 (9.56 MB/s) - ‘terraform_0.12.25_linux_amd64.zip’ saved [16736906/16736906]
    default: Archive:  terraform_0.12.25_linux_amd64.zip
    default:   inflating: terraform
    default: /home/vagrant
==> default: Running provisioner: file...
    default: ./hello.go => hello.go
==> default: Running provisioner: shell...
    default: Running: /var/folders/cl/pb51l2dx2050qg0vpbwg_tv40000gq/T/vagrant-shell20210713-88127-z9d09y.sh
```

### Check the program has been compiled successfully


### Sample output

```
vagrant ssh -c "./hello"
hello world
Connection to 127.0.0.1 closed.
```

### Check build status in Travis

### Import the repo in GitHub

![image](https://user-images.githubusercontent.com/85481359/125571521-6890e462-1258-4100-8f3a-5c6047815f50.png)

### Check the build in travis-ci.com

![image](https://user-images.githubusercontent.com/85481359/125571873-a2885413-41ad-4e0a-957c-ed709e2d0f80.png)


### Create a TAG in GitHub

![image](https://user-images.githubusercontent.com/85481359/125578189-08b7e3ec-4dad-4e91-9584-d6fac0cbd1fc.png)


![image](https://user-images.githubusercontent.com/85481359/125578336-29320ba1-b766-40ff-b719-14d20d87f5f9.png)


![image](https://user-images.githubusercontent.com/85481359/125578562-325c9d8a-6e3d-421f-897e-37878256b6dd.png)


### Check your build in travis-ci has run the deployment successfully

![image](https://user-images.githubusercontent.com/85481359/125579016-d1703ccd-c437-48f3-a502-8bb89fd208cf.png)


### Back to the GitHub repo, the hello file should now be available in your release

![image](https://user-images.githubusercontent.com/85481359/125579193-b9727407-4287-4754-9fca-9cb3e1692099.png)



Vagrant Jenkins Example
=======================

This guide will explain how run a vagrant image and install Jenkins

### Prerequisite

* Vagrant (https://www.vagrantup.com)
* Virtual Box (https://www.virtualbox.org)
* Git (http://git-scm.com)

### Step 1

Clone the repo:

```
git clone git@github.com:mooreandrew/vagrant-jenkins-example.git
```

### Step 2

Edit the provision file and add the following:

```
wget -q -O - https://jenkins-ci.org/debian/jenkins-ci.org.key | sudo apt-key add -
sh -c 'echo deb http://pkg.jenkins-ci.org/debian binary/ > /etc/apt/sources.list.d/jenkins.list'
apt-get update
apt-get install jenkins
service jenkins start
```
Note: These commands are based on the ones from: https://wiki.jenkins-ci.org/display/JENKINS/Installing+Jenkins+on+Ubuntu

With the following differences:
* Vagrant runs the provision as the super user (so no sudo prefix needed)
* apt-get is being done silently (-qy command)
* The start service command was missing.

### Step 3

From the command line, type:

```
vagrant up
```

### Step 4

Jenkins should now be running. You can access it from:

```
http://localhost:8080
```

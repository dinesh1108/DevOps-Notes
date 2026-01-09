# Installation of SELinux

1. Install Required SELinux Packages:

Run the following command to install the necessary SELinux utilities (if they are not already installed:<br>

`sudo yum install -y policycoreutils policycoreutils-python-utils selinux-policy-targeted`

_(Note: In some minimal environments, `libselinux-utils` might be the specific package needed, but the command above covers the standard toolset.)_

2. Disable SELinux:

* &#x20; Open the file:
* `sudo vi /etc/selinux/config`

Find the line that starts with `SELINUX=`

Change it to:

<mark style="color:$success;">`SELINUX`</mark>`=disabled`

3. Save and exit (`:wq`).

#### Verification

You can confirm the file was updated correctly by running:

```
cat /etc/selinux/config | grep SELINUX=disabled
```

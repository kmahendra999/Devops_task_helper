<pre>
Patching in Linux
============================
to see installed software:
yum list installed
rpm -qa

Need to check how we will get update


check which os:
cat /etc/os-release

check repo by redhat:
cat /etc/yum.repos.d/redhat-rhui*

------------------------
What all packing are going to be upgrade:

for check update of available softwares:
yum check-update

Note: Before upgrading the package in prod test the upgrade in SIT(System Integration Testing)/QA/TEST

check repos in our system:
yum repolist

for update:
yum update -y

start installinng the upgrade.


============================================
for test process ensure:
before reboot
yum check-update
see in last the what will be effects.

then reboot

Note : after patching reboot the system after done. its recommanded.

after reboot run
yum check-update

for rolling back :
take snapshot of vm before patch

</pre>

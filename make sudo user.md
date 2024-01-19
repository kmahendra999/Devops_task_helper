REfrence :https://docs.rackspace.com/docs/create-sudo-user-in-centos

#useradd admin

#passwd admin

give password Example redhat

#visudo
i for insert mode

below line add for user admin also
##Allow root to run any commands anywhere
root    ALL=(ALL)       ALL
admin   ALL=(ALL)       ALL

save file by :wq!

done! Go

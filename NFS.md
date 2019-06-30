# Network File System (NFS)

>The Network File System (NFS) is a way of mounting Linux discs/directories over a network. An NFS server can export one or more directories that can then be mounted on a remote Linux machine.In other words, It is a client/server system that allows users to access files across a network and treat them as if they resided in a local file directory. Note that if you need to mount a Linux filesystem on a Windows machine, you need to use Samba/CIFS instead.

### At Server-end
    # yum install bash-completion
    // to enable auto-complete using tab

    # yum install nfs-utils
    # systemctl start nfs-server
    # systemctl enable nfs-server.service

    # mkdir /nfs
    # rpm -qc nfs-utils (to see config files)

    # vi /etc/exports
        make entry :--> /nfs    *(ro)       // read only
                             or
                        /nfs    *(rw)       // read write       
                            and change permission        (-- drawback : other user can also work in that directory)
                            or
                        /nfs    *(rw,no_root_squash)    (-- root permission dene ke liye client ip ko)
    # exportfs -r       (r=relode)

    # showmount -e (public Ip)          (--It will show shared files)

### At Client-end 

        # showmount -e Ip(private Ip of server)
        # mount Ip:/nfs /mnt/nfs
        (IP is private Ip)
        Why not use public ip for nfs?

        fstab entry : serverIP:/nfs  /mnt/nfs  nfs  _netdev  0  0

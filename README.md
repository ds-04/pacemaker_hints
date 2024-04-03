# pacemaker_hints
pacemaker_hints - collection of commands or procedures to help managing pacemaker/corrosync


maintenance mode:

``pcs property set maintenance-mode=true``

list contraints:

``pcs constraint list --full``


disable stonith:

``pcs property set stonith-enabled=false``


forget failed stonith operations on nodename:

``pcs stonith history cleanup nodename``

forget failed operations and limit using strict, to avoid impacting resource group (check man page on this one):

``pcs resource cleanup service-my-daemon --strict``


rhel7 guide on resource creation:

https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/high_availability_add-on_administration/s1-resourcegroupcreatenfs-haaa


rhel8 guide on constraints:

https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/configuring_and_managing_high_availability_clusters/assembly_determining-which-node-a-resource-runs-on-configuring-and-managing-high-availability-clusters


<h1>Example systemd pcs resource</h1>


``pcs resource create myservice systemd:myservice.service --group myservicegroup-example``

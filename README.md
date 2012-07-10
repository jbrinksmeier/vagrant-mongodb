Vagrant plugin and puppet manifests for MongoDB
===============================================

Creates (by default) 3 virtual machines based on Ubuntu Lucid (64bits).
Syncrhonizes their /ets/hosts files, and provisions them with MongoDB
from the official 10gen repository (currently v2.0.6).

Several new Vagrant configurations are available in the Vagrantfile
to configure a MongoDB replicaset, such as the servers priority.

A new Vagrant comand is availalbe to initialize the replicaset based on
the configuration in the Vagrantfile.


Usage
-----
    $ git clone https://github.com/bjori/vagrant-mongodb-replicaset.git
    $ cd vagrant-mongodb-replicaset
    $ vagrant up && vagrant mongo primary --init-replicaset


You may want to add the following entries to your /etc/hosts

    172.16.1.10 primary.rs.local primary
    172.16.1.11 secondary.rs.local secondary
    172.16.1.12 tertiary.rs.local tertiary


And there we go!
Now you have a full MongoDB replicaset running in its own virtualized network.
To connect to it, fire up your favorite driver and connect to either the primary
og secondary hostnames, on the default port.

Tata!

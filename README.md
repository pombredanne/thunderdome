thunderdome
===========

thunderdome is an object-graph mapper (OGM) designed specifically for use with
Titan (http://thinkaurelius.github.com/titan/) via Rexster
(https://github.com/tinkerpop/rexster/wiki). Thunderdome supports easily
integrating Gremlin graph-traversals with vertex and edge models. For those
already familiar with Blueprints (https://github.com/tinkerpop/blueprints/wiki)
the following is a simple example:

Installation
============

To install thunderdome you will need to clone the repository and add it to your python path.

```shell
$ git clone git@github.com:StartTheShift/thunderdome.git path/to/thunderdome
$ export PYTHONPATH = path/to/thunderdome:$(PYTHONPATH)
```

To make the PYTHONPATH change permanent you can add it to your .bashrc or .zshrc file.

Quick start
===========

A [Vagrant](http://www.vagrantup.com/) virtual environment is provided with the
thunderdome repository. To get the virtual environment up and running simply do
the following:

```shell
$ cd path/to/thunderdome
$ vagrant up
...
$ vagrant ssh
...
vagrant@precise64:~$ cd /vagrant
```

This will put you in the thunderdome directory in the vagrant box. You can now
run the unit-tests or start playing around within the python shell.

Check out the [Quick Start](thunderdome/wiki/Quick-Start) page for a simple
introduction to working with thunderdome.

Unit-tests
==========

To get thunderdome unit tests running you'll need a rexster server configured with a thunderdome graph.  

``` xml
<graph>
    <graph-name>thunderdome</graph-name>
    <graph-type>com.thinkaurelius.titan.tinkerpop.rexster.TitanGraphConfiguration</graph-type>
    <graph-read-only>false</graph-read-only>
    <graph-location>/tmp/thunderdome</graph-location>
    <properties>
          <storage.backend>local</storage.backend>
          <storage.directory>/tmp/thunderdome</storage.directory>
          <buffer-size>100</buffer-size>
    </properties>

    <extensions>
      <allows>
        <allow>tp:gremlin</allow>
      </allows>
    </extensions>
</graph>
```

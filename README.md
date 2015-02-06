node-kernel
===========

A [node.js](http://nodejs.org/) kernel for [ipython](http://ipython.org/).

##INSTALL

Assumes you have already installed ipython and node.js.

1. run `ipython profile create node`
2. add the following to `~/.ipython/profile_node/ipython_notebook_config.py`
```
c = get_config()
c.ZMQInteractiveShell.debug = True
c.ZMQInteractiveShell.pdb = True
#assumes node-kernel dir is ~/node-kernel
c.KernelManager.kernel_cmd = ["/usr/local/bin/node", "--debug",
                              "node-kernel/kernel.js", "{connection_file}"]
c.Session.key = ''
c.Session.debug = True
c.Session.keyfile = ''
```
3. run `npm install`
4. run `ipython notebook --profile=node`


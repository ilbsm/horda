### **How to run Jupyter notebooks remotely on HORDA?**

Assuming <code>jupyter</code> is running on <code>troll-1</code> (port <code>8888</code>) 
and that the connection is established with <code>sshuttle</code> (see [**Getting started**](first_steps.md#connecting-via-ssh)
section for more details) it is possible setup the tunnel as follows:
```sh
ssh -NL 8888:localhost:8888 your_username@troll-1.sih-60.internal
```

Afterwards you should be able to see the running Jupyter instance via browser at the URL:
<code>http://localhost:8888</code>

### **How to install python packages on HORDA?**
<code>python3</code> (3.10 and 3.11) as well as  <code>python2</code> (2.7.18) along with the recent <code>pip</code> 
and <code>venv</code> are installed system-wide on each node of HORDA.

You can simply install packages either with <code>pip install --user</code> or use <code>venv</code> or <code>svirtualenv</code>
(this will allow to handle multiple projects with possibly conflicting dependencies).

Finally, if you need newer versions of <code>python</code> or want to handle complicated dependencies you can install a
local version of <code>anaconda</code> in your <code>$HOME</code> directory.

### **I want to use program <code>XXX</code> on HORDA, can I install it on my own?**

You can install any software you like in your <code>$HOME</code> directory (as long as you have a valid license to use it).

If you need support in setup of some program or want it to be installed system-wide, please contact the administrators.

[//]: # (### **What are the guidelines for <code>/home/nfs/</code> distributed filesystem use?**)

[//]: # ( )
[//]: # (- Store only the necessary data in your <code>/home/nfs/your_username</code> directory. The space in this filesystem is limited.)

[//]: # (    - For example: storing your conda distribution, scripts, inputs for jobs run on the cluster and small outputs)

[//]: # (that you'll move to personal space after completion of the calculations is **OK**. )

[//]: # (- Avoid prolonged and heavy I/O operations &#40;like reading and writing large files&#41;.)

[//]: # (    - For example: Writing output from the MD simulations in <code>amber</code> &#40;successive, small write operations&#41; is **OK**.)

[//]: # (Reading a 100 GB file from <code>nfs</code> directory is **not OK**.)

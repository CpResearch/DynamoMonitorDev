Dyanmo Monitor Development
==========================


Copy Latest Data
----------------

<your server> (ex. t3serv016) will be a clone of t3serv009. Install dynamo and dynamo-mitlocal under
your account (ex. Work/).

 # make directory
 mkdir ~/Work
 cd ~/Work
 cp -r ~cmsprod/Work

 # for updated installation do
 /root/dynamo-mitlocal/install.sh ../dynamo
 /etc/init.d/dynamod


Data Content
------------

First edit the data content of the web page you are producing by editing a file like:

  https://github.com/SmartDataProjects/dynamo/blob/master/lib/web/modules/transfers/monitor.py


The Web Template
----------------

An example of a static web template is given in:

  https://github.com/SmartDataProjects/dynamo/blob/master/web/html/transfers/monitor_static.html


Develop Some Code and See What it Does
--------------------------------------

Any student can do this in private on their own clone server machine. Careful, we need to coordinate the github activity not to loose any work.

Step 0: get the project

  git clone git://github.com/SmartDataProjects/dynamo-mitlocal

  git clone git://github.com/SmartDataProjects/dynamo
  cd dynamo
  git checkout -b monitor-ugrads

Step 1: make some adjustments to the code

  edit code as approriate

Step 2: install the new code in the running program

  # install it to the machine
  /root/dynamo-mitlocal/install.sh
  
  # restart the server
  /etc/init.d/dynamod stop
  /etc/init.d/dynamod start

Step 3: look at the monitor page to see your result

  Go to:

  http://t3serv009.mit.edu/web/transfers/list

  'transfers' comes from directory structure in dynamo/lib/web/modules
  'list' comes from the export_web dictionary in dynamo/lib/web/modules/transfers/monitor.py

Step 4: Commit your changes to our branch (monitor-undergrads)

  only whe you are happy with your changes.

  cd dynamo
  git commit -am 'Test'
  git push origin monitor-ugrads


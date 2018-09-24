Dyanmo Monitor Development
==========================


Copy Latest Data
----------------

<your server> (ex. t3serv016) will be a clone of t3serv009. Install dynamo and dynamo-mitlocal under your account (ex. Work/).

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



Standard Plots for Data Management Operations
---------------------------------------------

To produce a plot of any data management opertations(transfer of deletion) there are a number of selection parameters we should be able to specify. The selectable quantities are:

  * date(min,max),
  * grouping(source,target,link), exitcode(*,one,!one)
  * expert sql statement

 - transfer activity versus time
   - number of
   - volume
   - rates (+n,v)
   - cumulative volume
   + 2D for links?
   + error rate (n_error/n_all)

 - deletion activity versus time
   - number of
   - volume
   - rates (n,v)
   - cumulative volume
   + error rate (n_error/n_all)

 - properties
   + file size
   + duration [tune time out]
   + single rate
   + error codes

Lists
=====

 - selectable: date(min,max), grouping(source,target,link), exitcode(*,one,!one)
               - lfn like "sql string"

 - content of list
   - lfn
   - source
   - target
   - exitcode
   - created
   - started
   - finished

 - full history of a given file: deletion, transfer ordered chronologically


Plot grouping
=============

 - standard plots for each site
 - standard plots for a given sample

# Installation Tutorial

[1. Installing from MacPorts](#install-mysql-with-macports)

[2. Copying the default config](#copy-the-default-config)

[3. Activate the LaunchDaemon](#activate-the-launchdaemon)

[4. Set the mysql root password](#set-the-mysql-root-password)

[5. Use mysql](#use-mysql)




## Install mysql with MacPorts

```bash
sudo port install mysql56-server mysql56
```

```bash
sudo port select --set mysql mysql56
```

## Copy the default config

*Try*
```bash
sudo -u _mysql /opt/local/lib/mysql56/bin/mysql_install_db
```
If it returns **Permission denied**, then it should suggest a manual copy.
In this case, use
```bash
sudo cp $FP1 $FP2;
sudo chmod a+w $FP2
```

## Activate the LaunchDaemon
```bash
sudo port load mysql56-server
```

**Now reboot your computer**

## Set the mysql root password

```bash
/opt/local/lib/mysql56/bin/mysqladmin -u root password 'new-password'
```

## Use MySql

The mysql56 client is now mapped to `mysql` in the command line. 
Before you start using mysql, you will probably want to add some users, create some databases, and set the permissions on those databases for the users.

For tips on how to setup the database, see [this](http://www.codesynthesis.com/pipermail/odb-users/2014-January/001692.html)

References:
- http://stackoverflow.com/questions/27325754/setup-mysql-5-6-with-macports
- http://www.codesynthesis.com/pipermail/odb-users/2014-January/001692.html


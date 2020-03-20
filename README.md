# Datomic-Guide
Just another guide for working with the Datomic database (hopefully one that's somewhat straightforward).


1. Download the Files

Datomic Free - https://my.datomic.com/downloads/free

Datomic Starter Pro - https://my.datomic.com/downloads/pro

### Why both?
The starter pro is the "recommended" way to go, but the free version contains the script for the console files.

2. Add license key (if using starter pro)
```
vim config/samples/dev-transactor-template.properties
```

You should have received a license key via email. Add this license as the value for `license-key=` and then save & quit the file.


3. Run the transactor

If using starter pro:
```
bin/transactor config/samples/dev-transactor-template.properties
```

If using free:
```
bin/transactor config/samples/free-transactor-template.properties
```

4. Run the peer server
```
bin/run -m datomic.peer-server -h localhost -p 8998 -a myaccesskey,mysecret -d hello,datomic:mem://hello
```

5. Install console (if running the starter version) 
The console only comes with datomic free, so to use it with the starter pro you need to fun the install script from the datomic free folder and point it at the starter folder
```
bin/install-console ~/Downloads/datomic-pro-0.9.6045
```

5. Run the console
```
bin/console -p 8080 dev datomic:dev://localhost:4334/
```

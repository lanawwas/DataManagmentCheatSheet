#declare db path 
```
./mongodb/bin/mongod --dbpath db 
```
#start mongoDB server 
```
./mongodb/bin/mongo
```

#show databases and collections 
```
show dbs
```
#switch to databases 
```
use <database_name>
```
#list the current db indexes 
```
db.<db_name>.getIndexes()
```
#drop current index
```
db.<db_name>.dropIndex("<index?name>")
```
###Query
#Count number of null values in a nested field in database 
db.<database_name>.find('<field?name>.<nested?field>: null).count()

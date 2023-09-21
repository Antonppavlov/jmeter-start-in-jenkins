influxdb

```
docker run -d --name=influxdb --restart=always -p 8086:8086 -e INFLUXDB_ADMIN_USER=admin -e INFLUXDB_ADMIN_PASSWORD=admin -v /Users/antonpavlov/Documents/influxdb:/var/lib/influxdb influxdb:1.8.3
docker run -d --name=influxdb --restart=always -p 8086:8086 -v /Users/antonpavlov/Documents/influxdb:/var/lib/influxdb influxdb:1.8.3
```

```
docker exec -it influxdb bash
```

```
influx
```

```
show databases
```

```
create database jmeter
```

```
use jmeter
```
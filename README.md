```shell
pwd; 
ls -ltrh;
java -version;
curl https://dlcdn.apache.org//jmeter/binaries/apache-jmeter-5.6.2.tgz -o apache-jmeter-5.6.2.tgz;
tar -xvzf apache-jmeter-5.6.2.tgz;
cd apache-jmeter-5.6.2/bin;
sh jmeter.sh -n -t ../../jmeter_start_in_jenkins.jmx -l result.jtl -Jhost=wordpress
```
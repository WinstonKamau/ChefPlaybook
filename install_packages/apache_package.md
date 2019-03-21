To add a pacakge on an Ubuntu instance you can run the command below on the apache_package.rb file

```
chef-client --local-mode apache_package.rb
```

Ideally the assumption is that chef-client has been installed on the Ubuntu instance. 
The script is meant to update the cache daily, install apache package and createa html page with the name Hello world. This can be confirmed by viewing what is on the localhost

```
curl localhost
```
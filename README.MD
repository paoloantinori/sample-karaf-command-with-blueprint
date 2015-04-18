Sample Karaf command that uses Blueprint to plug into OSGi framework.
---------------------------------------------------------------------

A very simple tutorial to expose your custom POJO as an Apache Karaf command, using Blueprint.

##### To build
```
maven clean install
```

##### To deploy on karaf:
```
# any karaf supported way, ex.
install -s file:///tmp/gogo/sample-karaf-command-with-blueprint/target/custom-karaf-command-1.0.jar
```

##### Usage:
```
JBossFuse:karaf@root> your_namespace:first
first
JBossFuse:karaf@root> your_namespace:second
second
JBossFuse:karaf@root> your_namespace:hello world
hello world
```

##### Note:
This won't enlist your command automatically on Karaf console when you will press tab.
The command will be there though, you can verify with:
```bash
JBossFuse:karaf@root> $.commands | grep your_namespace
your_namespace:first
your_namespace:second
your_namespace:hello
```

If you want a solution that integrates better with the platform but that will force you to be "platform aware". I suggest you this tutorial:

http://icodebythesea.blogspot.it/2011/11/creating-your-own-apache-karaf-console.html


# Data browser

Databrowser is a web app to explore the data in a Crux database. Read more in the blogpost: https://thegeez.net/2020/07/16/databrowser_crux.html

# Instructions

Download the jar file from: https://github.com/thegeez/databrowser/releases/tag/v1.0.0-512_3

#### Using the jar with deps.edn
Include the jar file in your projects dependencies in deps.edn:
```clj
net.thegeez.databrowser/databrowser-crux {:local/root "/PATH_TO_JAR/databrowser-crux-1.0.0-512_3.jar"}
```

Add the databrowser to your Crux topology:
```clj
(require 'net.thegeez.databrowser)
(crux/start-node {:crux.node/topology '[crux.standalone/topology
                                        net.thegeez.databrowser/module
                                       ]
                  :net.thegeez.databrowser/port 3344
                  })
```


#### Using the jar with lein
Install the jar into maven locally:
```
unzip -p /PATH_TO_JAR/databrowser-crux-1.0.0-512_3.jar META-INF/maven/net.thegeez.databrowser/databrowser_crux/pom.xml > pom.xml

mvn install:install-file -Dpackaging=jar -Dfile=/PATH_TO_JAR/databrowser-crux-1.0.0-512_3.jar -DpomFile=pom.xml
```
Include the jar file in your project.clj:
```clj
[net.thegeez.databrowser/databrowser-crux "1.0.0-512_3"]
```



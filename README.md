# Data browser

Databrowser is a web app to explore the data in a Crux database. Read more in the blogpost: https://thegeez.net/2020/07/16/databrowser_crux.html

# Instructions

Download the jar file from: https://github.com/thegeez/databrowser/releases/tag/v1.0.0-512_3

Include the jar file in your projects dependencies:
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
       

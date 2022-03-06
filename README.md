## Architecture

```
      + - - - - - +
      |  BROWSER  |
      + - - - - - +
            |
            |
            | - - - - - - - - - - >|
            |                      |
            |                      |                                public
  -------------------------------------------------------------------------
           /\                      /\                                  k8s
           ||                      ||
           ||                      ||
           ||                      ||
           ||                      ||
         (4100)            (web-backend:8080)
    +--------------+       +-----------------+             +-----------+
    |              |       |                 |             |           |
    |   FRONTEND   |       |     BACKEND     |-------(3600)|     DB    |
    |  (js-react)  |       |  (java-spring)  |             |  (mysql)  |
    |              |       |                 |             |           |
    +--------------+       +-----------------+             +-----------+
```

## resources
  - https://www.eclipse.org/che/docs/che-7/making-a-workspace-portable-using-a-devfile/
  - https://github.com/redhat-developer/devfile
    - https://redhat-developer.github.io/devfile/
    - https://redhat-developer.github.io/devfile/devfile


## che.openshift.io
  - che - https://che.openshift.io
  - OS console - https://console.starter-us-east-2.openshift.com
  - factory without db - https://che.openshift.io/f?url=https://raw.githubusercontent.com/sparkoo/devconf-2020-devfile/master/steps/07-commands.yaml
  - factory with db - https://che.openshift.io/f?url=https://raw.githubusercontent.com/sparkoo/devconf-2020-devfile/master/devfile.yaml


### db
**build.gradle**
```
runtime('mysql:mysql-connector-java')
```
**application.properties**
```
database=mysql
spring.datasource.url=jdbc:mysql://db:3306/demo
spring.datasource.username=demo
spring.datasource.password=demo
```

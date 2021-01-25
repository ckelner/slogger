# slogger
Syslog Generator - taken from http://syslog-slogger.sourceforge.net/

## Build Java
- Classes:
  - `javac -d bin -cp 3rdParty/Syslog.jar src/org/slogger/*.java`
    - Produces `*.class` in `./bin`
- Jar:
  - `cd ./bin`
  - `jar cvfm ../slogger.jar ../MANIFEST.mf *`
    - Produces `slogger.jar` in `.`

## Run Jar
- `java -jar slogger.jar`
  - Should produce output:
    ```
    ⇒  java -jar slogger.jar
    Slogger v0.6
    Usage java org.slogger.Slogger <PropertiesFileName>
    Slogger will attempt using ./slogger.properties
    Slogger v0.6 running.
    # syslogs generated 100 @0 eps
    slogger generated 100 syslogs  in 0.1 secs @ 1000 eps
    Completed in 0.162 secs.
    ```
  - Will create `./syslog.log`

## To Publish to Network
- In `./slogger.properties` comment out the `FilePublisher` and uncomment
`NetworkPublisher`:
  ```
  syslogPublisher=org.slogger.publisher.FilePublisher
  #syslogPublisher=org.slogger.publisher.NetworkPublisher
  ```

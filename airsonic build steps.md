# airsonic build steps

## Base project context
`cd /Users/zachvp/developer/repos/airsonic-advanced`

### Base project build
```
mvn clean compile package install verify -DskipTests -Dcheckstyle.skip=true --settings ~/developer/repos/airsonic-advanced/.mvn/settings.xml
```

## Docker context
`cd /Users/zachvp/developer/repos/airsonic-advanced/install/docker`

## Docker build image
```
mvn clean compile package install -U -DskipTests -Dcheckstyle.skip=true --settings ../../.mvn/settings.xml
```

## Docker run container
```
docker run -p 8001:4040/tcp -p 8002:4041/tcp -v /Users/zachvp/developer/test-private/data/tracks:/var/music --name airsonic-test airsonicadvanced/airsonic-advanced:latest
```

## Docker teardown
```
docker container rm airsonic-test
```

# Recent flagged files
* MediaFileEntry.java
* MediaFile.java
* MediaFileService.java
* StringUtil.java
* externalPlayer.jsp
* ExternalPlayerController.java
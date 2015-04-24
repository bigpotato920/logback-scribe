This project provides logback Appender who sends log messages to Facebook Scribe (a log server)


See: https://github.com/facebook/scribe/

# How to use it #

**Current release:** 1.0.0

## Maven style ##

Add our repository:
```
<repository>
	<id>release</id>
	<name>Bitzeche Releases</name>
	<url>http://trac.bitzeche.de/archiva/repository/release/</url>
</repository>
```

And add a dependency:
```
<dependency>
	<groupId>de.bitzeche.logback</groupId>
        <artifactId>logback-scribe</artifactId>
        <version>1.0.0</version>
</dependency>
```

## Manual ##

Dependencies:
  1. Logback
  1. Thrift
  1. fb303
  1. TestNG
  1. Mockito

## Implement it ##
Change your logback.xml and add a new appender (example):
```
<appender name="Scribe" class="de.bitzeche.logback.scribe.ScribeAppender">
	<hostname>localhost</hostname>
	<layout>
		<pattern>${HOSTNAME} %d{HH:mm:ss.SSS} [%thread] %-5level %logger{36} - %msg%n</pattern>
	</layout>
	<scribeCategory>myCategory</scribeCategory>
</appender>

<root level="info">
	<appender-ref ref="Scribe" />
</root>
```

# Contribute #

If you have a suggestion or a patch or want to contribute in any form to the project, feel free to contact us.
Help is always very welcome.
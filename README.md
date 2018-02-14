[![Build Status](https://travis-ci.org/javadelight/delight-factories.svg?branch=master)](https://travis-ci.org/javadelight/delight-factories)

delight-factories
=========

A simple API for factories based on simple plain Java objects.

Part of [Java Delight](https://github.com/javadelight/delight-main#java-delight-suite).

## Usage


Create a collection of factories:

```java
FactoryCollection factories = Factories.create();
```

Define classes for a factory:

```
private static class MyConfiguration implements Configuration {}
	
private static class MyDependencies implements Dependencies {}
```

Register a factory:

```java

factories.register(new Factory<String, MyConfiguration, Dependencies>() {

	@Override
	public boolean canInstantiate(Configuration conf) {
		return (conf instanceof MyConfiguration);
	}

	@Override
	public String create(MyConfiguration conf, Dependencies dependencies) {
		
		return "Hello, World!";
	}
	
});
```

Instantiate an object:

```java
Object created = factories.create(new MyConfiguration(), new MyDependencies());
// created == "Hello, WorlD!";
```

## Maven Dependency

```xml
<dependency>
    <groupId>org.javadelight</groupId>
    <artifactId>delight-factories</artifactId>
    <version>[insert latest version]</version>
</dependency>
```

This artifact is available on [Maven Central](https://search.maven.org/#search%7Cga%7C1%7Cdelight-factories) and 
[BinTray](https://bintray.com/javadelight/javadelight/delight-factories).

[![Maven Central](https://img.shields.io/maven-central/v/org.javadelight/delight-factories.svg)](https://search.maven.org/#search%7Cga%7C1%7Cdelight-factories)


## Links

-> [All Project Reports](http://modules.appjangle.com/delight-factories/latest/project-reports.html)


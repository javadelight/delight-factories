[![Build Status](https://travis-ci.org/javadelight/delight-factories.svg?branch=master)](https://travis-ci.org/javadelight/delight-factories)

delight-factories
=========

A simple API for factories.

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
		
		return "Hello, World again!";
	}
	
});
```

## Links

-> [All Project Reports](http://modules.appjangle.com/delight-factories/latest/project-reports.html)


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
	
private static class MyOtherConfiguration implements Configuration {}
```

Register a factory:

```java

factories.register(new Factory<String, MyOtherConfiguration, Dependencies>() {

	@Override
	public boolean canInstantiate(Configuration conf) {
		return (conf instanceof MyOtherConfiguration);
	}

	@Override
	public String create(MyOtherConfiguration conf, Dependencies dependencies) {
		
		return "Hello, World again!";
	}
	
});
```

## Links

-> [All Project Reports](http://modules.appjangle.com/delight-factories/latest/project-reports.html)


jsoniter (json-iterator) is fast and flexible JSON parser available in [Java](https://github.com/json-iterator/java) and [Go](https://github.com/json-iterator/go)

# Why jsoniter?

* Jsoniter is the fastest JSON parser. It could be up to 10x faster than normal parser, data binding included. Shameless self [benchmark](http://jsoniter.com/benchmark.html)
* Extremely flexible api. You can mix and match three different styles: bind-api, any-api or iterator-api. Checkout your [api choices](http://jsoniter.com/api.html)
* Unique iterator api can iterate through JSON directly, zero memory allocation! See how [iterator](http://jsoniter.com/api.html#iterator-api) works

# Show off

Here is a quick show off, for more complete report you can checkout the full [benchmark](http://jsoniter.com/benchmark.html) with [in-depth optimization](http://jsoniter.com/benchmark.html#optimization-used) to back the numbers up

![java1](http://jsoniter.com/benchmarks/java1.png)

# 1 Minute Tutorial

Given this JSON document `[0,1,2,3]`

Parse with Java bind-api

```java
import com.jsoniter.Jsoniter;
Jsoniter iter = Jsoniter.parse("[0,1,2,3]");
int[] val = iter.read(int[].class);
System.out.println(val[3]);
```

Parse with Java any-api

```java
import com.jsoniter.Jsoniter;
Jsoniter iter = Jsoniter.parse("[0,1,2,3]");
Any val = iter.readAny();
System.out.println(any.get(3));
```

Parse with Java iterator-api

```java
import com.jsoniter.Jsoniter;
Jsoniter iter = Jsoniter.parse("[0,1,2,3]");
int total = 0;
while(iter.readArray()) {
    total += iter.readInt();
}
System.out.println(total);
```

# How to get

```
<dependency>
    <groupId>com.jsoniter</groupId>
    <artifactId>jsoniter</artifactId>
    <version>0.9.1</version>
</dependency>
```

# Contribution Welcomed !

Report issue or pull request, or email taowen@gmail.com, or [![Gitter chat](https://badges.gitter.im/gitterHQ/gitter.png)](https://gitter.im/json-iterator/Lobby)
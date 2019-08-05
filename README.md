[ ![Download](https://api.bintray.com/packages/corx/maven/KUtils/images/download.svg) ](https://bintray.com/corx/maven/KUtils/_latestVersion) 
[![Apache License 2.0](https://img.shields.io/github/license/coderinx/kutils.svg)](https://github.com/Coderinx/KUtils/blob/master/LICENSE)

# KUtils
Useful functions for kotlin

## Using in your projects

The library is published to [kutils](https://bintray.com/corx/maven/KUtils) bintray repository and linked to [JCenter](https://bintray.com/bintray/jcenter?filterByPkgName=KUtils-corx).

### Maven

Add dependency:

```xml
<dependency>
  <groupId>org.coderinx</groupId>
  <artifactId>kutils</artifactId>
  <version>0.2.1</version>
</dependency>
```


### Gradle

Add dependency:

```groovy
dependencies {
    implementation 'org.coderinx:kutils:0.2.1'
}
```

Make sure that you have `jcenter()` in the list of repositories:

```
repository {
    jcenter()
}
```

### Gradle Kotlin DSL

Add dependency:

```kotlin
dependencies {
    implementation("org.coderinx:kutils:0.2.1")
}
```

Make sure that you have `jcenter()` in the list of repositories:

```
repository {
    jcenter()
}
```


## Examples

### Time measurement

#### Measures time in `ms` by default
`withTimeMeasurement`

```kotlin
val (time, result) = withTimeMeasurement {
    Thread.sleep(2000)
    50 * 10
}
println("Result $result has been calculated for $time ms")
```
Output:
```
Result 500 has been calculated for 2001 ms
```

`measureTime`

```kotlin
val time = measureTime {
    Thread.sleep(2000)
    println("executing...")
}
println("Execution has been completed for $time ms")
```
Output:
```
executing...
Execution has been completed for 2001 ms
```

#### Use specific `java.util.concurrent.TimeUnit` if necessary:
`withTimeMeasurement`

```kotlin
val (time, result) = withTimeMeasurement(TimeUnit.MICROSECONDS) {
    Thread.sleep(2000)
    50 * 10
}
println("Result $result has been calculated for $time microseconds")
```
Output:
```
Result 500 has been calculated for 2004993 microseconds
```

`measureTime`

```kotlin
val time = measureTime(TimeUnit.NANOSECONDS) {
    Thread.sleep(2000)
    println("executing...")
}
println("Execution has been completed for $time ns")
```
Output:
```
executing...
Execution has been completed for 2003947161 ns
```

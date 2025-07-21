# JVM
* [A JVM Does That??? (2011) [pdf]](http://www.azulsystems.com/blog/wp-content/uploads/2011/03/2011_WhatDoesJVMDo.pdf)
* [Allocation on the JVM: Down the rabbit hole](http://jcdav.is/2016/07/11/JVM-allocation-secrets/)
* [Memory Layout of Objects in Java](https://www.baeldung.com/java-memory-layout)

# Native memory usage
* [Native Memory Allocation in Java](https://dzone.com/articles/native-memory-allocation-in-examples)
* [Logging vs Memory](https://tersesystems.com/blog/2020/07/09/logging-vs-memory/)
  > Even when you use a heap ByteBuffer for I/O, it is copied into a temporary direct ByteBuffer. The JDK caches one temporary buffer per thread, without any memory limits. As a result, if you call I/O methods with large heap ByteBuffers from multiple threads, your process can use a huge amount of additional native memory, which looks like a native memory leak. This can cause your process to unexpectedly run into memory limits and get killed.
* [Fixing Java's ByteBuffer native memory "leak"](https://www.evanjones.ca/java-bytebuffer-leak.html)
* [jvm-alloc-rate-meter](https://github.com/clojure-goes-fast/jvm-alloc-rate-meter)
* [Using pmap and gdb to find native memory leak](https://stackoverflow.com/questions/61002346/using-pmap-and-gdb-to-find-native-memory-leak)

# JCMD
```
# jcmd            // list of processes
# jcmd <PID> help // list of available commands
# jcmd <PID> help <command>
# jcmd <PID> GC.class_histogram
# jcmd <PID> GC.heap_dump
# jcmd <PID> GC.heap_info
# jcmd <PID> VM.native_memory
# jcmd <PID> VM.native_memory summary.diff
```

# JFR
```
# jcmd <pid> JFR.start settings=profile
# jcmd <pid> JFR.dump name=1 filename=/Users/MyUser/FILENAME.jfr
# jcmd <pid> JFR.stop

# java -XX:StartFlightRecording="disk=true, filename=memory-tracking.jfr, dumponexit=true, settings=profile" -cp classpath ...

# jfr view --verbose allocation-by-class memory-tracking.jfr
# jfr view --verbose allocation-by-site memory-tracking.jfr
```

Uruchamianie z kodu:
```
val recording = new jdk.jfr.Recording()l
recording.start();
// recording.enable(Class eventClass);
recording.dump(Path destination);
recording.stop(); 
```

# JFR Streaming
// TODO

# Java Mission Control
brew install --cask jdk-mission-control

# async-profiler
* [A Guide to async-profiler](https://www.baeldung.com/java-async-profiler)

Ma przewage nad JFR - widzi co sie dzieje na poziomie JVM i OS
Jezeli problem jest w apcke to 1 krok JFR.
Jezeli w apce nic nie widac to async-profiler 
```
asprof start -e alloc <pid>
asprof stop -o flamegraph f0 flamegraph.htmp <pid>
```

# Libraries
* [Dependency Injection with Dagger 2](https://www.future-processing.pl/blog/dependency-injection-with-dagger-2/)
* [The Netty project](http://netty.io/)
* [Prometheus](https://prometheus.io/)
* [Retrofit](http://square.github.io/retrofit/)
* [JMH - Java Microbenchmark Harness](http://tutorials.jenkov.com/java-performance/jmh.html)
* [Zipkin - a distributed tracing system](http://zipkin.io/)
* [Log4j 2 - RollingFileAppender example](https://www.boraji.com/log4j-2-rollingfileappender-example)

# Date and Time
* [ALL ABOUT JAVA.UTIL.DATE](https://codeblog.jonskeet.uk/2017/04/23/all-about-java-util-date/)
* [A beginner’s guide to Java time zone handling](https://vladmihalcea.com/2014/11/17/a-beginners-guide-to-java-time-zone-handling/)
* [Java 8 Time - choosing the right object](http://mattgreencroft.blogspot.com/2014/12/java-8-time-choosing-right-object.html)
* [Daylight saving time and time zone best practices](https://stackoverflow.com/questions/2532729/daylight-saving-time-and-time-zone-best-practices)

* [What's the default classpath when not specifying classpath?](http://stackoverflow.com/questions/8227682/whats-the-default-classpath-when-not-specifying-classpath)

* [Why @Nonnull annotation checked at runtime?](http://stackoverflow.com/questions/40847472/why-nonnull-annotation-checked-at-runtime)
* [Is it possible to make anonymous inner classes in Java static?](https://stackoverflow.com/questions/758570/is-it-possible-to-make-anonymous-inner-classes-in-java-static)

# Reflection
* [Java Enums: List enumerated values from a Class<? extends Enum>](http://stackoverflow.com/questions/1626901/java-enums-list-enumerated-values-from-a-class-extends-enum)

# Collections
* Java 8 ConcurrentHashMap has tree buckets if keys implement Comparable. That guarantees O(log N)

# Streams
* [Java – How to convert Array to Stream](https://www.mkyong.com/java8/java-how-to-convert-array-to-stream/)
* [sorting Lists after groupingBy](https://stackoverflow.com/questions/35872236/sorting-lists-after-groupingby)
* [Writing Comparators - The Java 8 Way](https://praveer09.github.io/technology/2016/06/21/writing-comparators-the-java8-way/)

# SSL/TSL
* [Unable to Connect to SSL Services due to PKIX Path Building Failed](https://confluence.atlassian.com/kb/unable-to-connect-to-ssl-services-due-to-pkix-path-building-failed-779355358.html)
* [Configure Truststore in Tomcat](https://stackoverflow.com/questions/21833732/configure-truststore-in-tomcat)

# BGGA Closures
* [Reaction to Actually Using the BGGA closure Prototype](http://hamletdarcy.blogspot.com/2008/02/reaction-to-actually-using-bgga-closure.html)
* [The Closures Controversy](www.javac.info/bloch-closures-controversy.ppt)
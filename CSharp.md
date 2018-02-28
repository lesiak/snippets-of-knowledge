# C#

## Releases
* [What's new in C# 7.2](https://docs.microsoft.com/en-gb/dotnet/csharp/whats-new/csharp-7-2)
* [Welcome to C# 7.1](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/welcome-to-c-7-1/)

# Random features
* [Constraints are not part of the signature](https://blogs.msdn.microsoft.com/ericlippert/2009/12/10/constraints-are-not-part-of-the-signature/)
* [C# 3.0 Return Type Inference Does Not Work On Method Groups](https://blogs.msdn.microsoft.com/ericlippert/2007/11/05/c-3-0-return-type-inference-does-not-work-on-method-groups/)
* [C# : How C# 6.0 Simplifies, Clarifies and Condenses Your Code](https://msdn.microsoft.com/en-us/magazine/dn879355.aspx)
* [Interpolated Strings (C# and Visual Basic Reference)](https://msdn.microsoft.com/en-us/library/dn961160.aspx)
* [Does C# have an equivalent of Java static nested class?](https://stackoverflow.com/questions/1581977/does-c-sharp-have-an-equivalent-of-java-static-nested-class)
* [Equivalent of Java's anonymous class in C#?](https://stackoverflow.com/questions/27273328/equivalent-of-javas-anonymous-class-in-c)
* [Is it possible to make an anonymous class inherit another class?](https://stackoverflow.com/questions/22226838/is-it-possible-to-make-an-anonymous-class-inherit-another-class)

# Unit tests
* [How to access classes in another assembly for unit-testing purposes?](https://stackoverflow.com/questions/1211707/how-to-access-classes-in-another-assembly-for-unit-testing-purposes)

# Debugging
* [Not Just My Code: How to debug third party libraries without decompiling them](https://medium.com/@jackspektor/not-just-my-code-how-to-debug-third-party-libraries-without-decompiling-them-8e47e706dbe7)

# Exceptions
* [Exceptions in Managed Threads](https://msdn.microsoft.com/en-us/library/ms228965(v=vs.110).aspx)
* [How to: Receive First-Chance Exception Notifications](https://msdn.microsoft.com/en-us/library/dd997368(v=vs.110).aspx)
* [AppDomain.FirstChanceException Event](https://msdn.microsoft.com/en-us/library/system.appdomain.firstchanceexception(v=vs.110).aspx)

# Async
* [C# 5 Async Exception Handling](http://www.interact-sw.co.uk/iangblog/2010/11/01/csharp5-async-exceptions)
* [Creating an observable sequence](http://www.introtorx.com/uat/content/v1.0.10621.0/04_CreatingObservableSequences.html)
* [Observable.FromAsyncPattern Method](https://msdn.microsoft.com/en-us/library/system.reactive.linq.observable.fromasyncpattern(v=vs.103).aspx)

# Code Security
* [Code Access Security Basics](https://msdn.microsoft.com/en-us/library/33tceax8.aspx)
* [SecureMethodAttribute Class](https://msdn.microsoft.com/en-us/library/system.enterpriseservices.securemethodattribute.aspx)

# Entity Framework
* [Entity Framework Database First](https://msdn.microsoft.com/en-us/library/jj206878(v=vs.113).aspx)
* [Entity Framework 6, database-first with Oracle](https://csharp.today/entity-framework-6-database-first-with-oracle/)
* [Forcing Entity Framework generated classes to have Pascal casing and column names to have Camel casing](https://stackoverflow.com/questions/15132067/forcing-entity-framework-generated-classes-to-have-pascal-casing-and-column-name)
* [10 Entity Framework 7 Features That You Must Know](http://www.c-sharpcorner.com/UploadFile/55d96a/10-entity-framework-7-features-that-you-must-know/)

# Linq
* [Linq code to select one item](https://stackoverflow.com/questions/7809745/linq-code-to-select-one-item)
* [Grouping lists into groups of X items per group](https://stackoverflow.com/questions/23921210/grouping-lists-into-groups-of-x-items-per-group)

# LinqConnect
* [LinqConnect Demo](https://www.devart.com/linqconnect/demo.html)
* [Eager Loading](https://www.devart.com/linqconnect/docs/EagerLoading.html)
* [Lazy Loading](https://www.devart.com/linqconnect/docs/LazyLoading.html)

# Assemblies
* [How the Runtime Locates Assemblies](https://msdn.microsoft.com/en-us/library/yx7xezcf(v=vs.110).aspx)
* [Specific version=false and GAC - what version will assembly use?](https://social.msdn.microsoft.com/Forums/en-US/3a344927-c24d-49dc-a025-47c7efc29ddd/specific-versionfalse-and-gac-what-version-will-assembly-use?forum=csharpide)
> To clarify, the build time assembly used isn't related to the runtime assembly used.  At runtime the loader will use the GAC to locate strongly named assemblies.  At build time VS does not use the GAC.  It always references a folder path outside the GAC for references.  Another thing to clarify is that the GAC only matters if the assembly is strongly named.  If the assembly is not then the GAC isn't relevant.  Finally note that Specific Version (SV) is strictly a build time attribute and has no impact on the runtime behavior.  As a result SV isn't impacted by the GAC at all.
> By default when you add a reference to an assembly VS will set it up such that it'll use the latest version.  SV will be false.  If you add the reference while the assembly was at 1.0.0.0 and then later update the assembly (in the referenced path) to 2.0.0.0 and rebuild then your app is suddenly using 2.0.0.0 instead.  This is generally what you want, hence it is the default. 
> However there are occassions where you want to build against a specific version of an assembly.  The version you build against was determined when you add the reference.  In this case you set SV to true.  Now if you replace the assembly in the referenced path with a new version the compiler is going to complain because it cannot use the specific version you had specified.
> None of this is relevant at runtime and therefore none of this is impacted by the GAC.  During compilation if the compiler finds a strongly named assembly then it puts the full assembly name into the metadata.  The version that will be stored depends upon SV and the version of the assembly that was found.  At runtime the loader uses a 2 step process to load the assembly.  If the loader determines that the assembly was strongly named then it uses the version number stored in the metadata.  Ignoring publisher policies, the loader will then look in the GAC for the exact version mentioned.  If the assembly cannot be found in the GAC then standard search path is used.  The loader requires that the exact version be found (again ignoring publisher policies).  If the assembly is not strongly named then the version is irrelevant and the loader will use the first one it finds.
> Going back to your scenario, since the assembly is strongly named the version that was used during compilation is baked into the metadata. At runtime the loader will search the GAC for the exact version.  It doesn't matter whether there are newer versions or not, the version that was built against will be used.  At compile time, since SV is false, the compiler will use the version of the assembly that it finds at the referenced path during compilation irrelevant of what version was originally used.  Whatever that version is will be the one looked for at runtime.
> Michael Taylor - 11/12/2012
> http://msmvps.com/blogs/p3net

* [Force .NET application to run in 32bit process on 64bit OS](https://lostechies.com/gabrielschenker/2009/10/21/force-net-application-to-run-in-32bit-process-on-64bit-os/)

* [.NET Core Image Processing](https://blogs.msdn.microsoft.com/dotnet/2017/01/19/net-core-image-processing/)

# Tools
* [dotPeek Symbol Server and PDB Generation](https://www.jetbrains.com/help/decompiler/2016.1/Symbol_Server_and_PDB_Generation.html)
* [Microsoft Help Viewer](https://msdn.microsoft.com/en-us/library/hh580782.aspx)
* [How do I find the .NET version?](https://stackoverflow.com/questions/1565434/how-do-i-find-the-net-version)
* [ASoft .NET Version Detector](http://www.asoft.be/prod_netver.html)

## Services
* [AppVeyor #1 Continuous Delivery service for Windows](https://www.appveyor.com/)
* [IdentityServer](https://identityserver.io/)
* [Bing Text to Speech API](https://docs.microsoft.com/en-us/azure/cognitive-services/speech/api-reference-rest/bingvoiceoutput)
* [Microsoft Bing Speech API: Windows Speech-to-Text Sample](https://azure.microsoft.com/en-gb/resources/samples/cognitive-speech-stt-windows/)

## Libraries
* [Serilog](https://serilog.net/)
* [NLog](http://nlog-project.org/)
* [DotNetty](https://github.com/azure/dotnetty)
* [Dapper - a simple object mapper for .Net](https://github.com/StackExchange/Dapper)
* [Nancy](https://www.hanselman.com/blog/ExploringAMinimalWebAPIWithNETCoreAndNancyFX.aspx)
* [App Metrics](http://app-metrics.io/)
* [Refit](https://github.com/paulcbetts/refit)
* [Zipkin4net](https://github.com/openzipkin/zipkin4net)

## .NetCore
* [Logging in .NET Core Console Applications](https://blog.bitscry.com/2017/05/31/logging-in-net-core-console-applications/)
* [Essential .NET - Dependency Injection with .NET Core](https://msdn.microsoft.com/en-us/magazine/mt707534.aspx)
* [How container actually resolve ILogger<T>](https://stackoverflow.com/questions/48672938/how-container-actually-resolve-iloggert)

# Gradle
Gradle is build tool, that helps you automate many things like: compiling your code, copying files, making artifacts like jar, zip. 
## Command line arguments
`gradle properties` - list all properties of project  
`gradle tasks` - list all available tasks of project  
`gradle -b buildFile` - use different file as build.gradle  
`gradle taskName -q` - display only task output
## Tasks
Task in gradle is atomic unit of work, that can have input/output and depend on other tasks.  
Task consist of action and dependencies.
## Properties
* You can define properties that can be access anywhere in build.gradle. This can be library version, filename etc.
```groovy project.ext.foo = "foo"
ext {
  retrofit_version = "2.3.0"
}
```
* Similary, additional properties can be defined in gradle.properties file.  
* Last way of defining properties is throw command line arguments  
Project property via the -P command-line option  
System property via the -D command-line option


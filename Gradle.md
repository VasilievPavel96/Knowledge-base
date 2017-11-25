# Gradle
Gradle is build tool, that helps you automate many things like: compiling your code, copying files, making artifacts like jar, zip. 
## Command line arguments
`gradle properties` - list all properties of project  
`gradle tasks` - list all available tasks of project  
`gradle -b buildFile` - use different file as build.gradle  
`gradle taskName -q` - display only task output
## Tasks
Task in gradle is self contained unit of work, that can have input/output and depend on other tasks.

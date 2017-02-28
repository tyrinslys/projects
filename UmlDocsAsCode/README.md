#UML Documents as Code
I am trying to get diagrams working for asciidoctor.
This was created using java 1.8 and gradle 3.4

## current state
fixed

Running 

    gradle asciidoctor

Should yeild the document to be generated using plantUML scripts.

## Trail
###I started 
with http://asciidoctor.org/docs/asciidoctor-gradle-plugin/
and tried to convert the script to gradle 3.3 format... works for any normal asciidoctor stuff but not if you add in a ditta diagram.

###I then 
added in things from here https://github.com/asciidoctor/asciidoctor-gradle-examples/blob/5f88408e1788562ff363dbb61e2de04f0fd11121/asciidoc-diagram-to-html-example/build.gradle
and converted them to the 3.3 format but that gives an error with

What went wrong:

    A problem occurred evaluating root project 'TryFromAsciiDoctorSite'.
    > Could not get unknown property 'jrubyPrepareGems' for task ':asciidoctor' of type org.asciidoctor.gradle.AsciidoctorTask.

###Found out that
`dependsOn jrubyPrepareGems` should have been `dependsOn jrubyPrepare` now seems to work



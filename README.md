# Open Test Alliance for the JVM

[![Travis Build Status](https://travis-ci.org/ota4j-team/opentest4j.svg?branch=master)](https://travis-ci.org/ota4j-team/opentest4j)

## History

This project is the result of an initiative by the [JUnit 5 team](https://github.com/junit-team/junit5/issues/12).

## Status Quo

There is no standard for testing on the JVM: the only common building block we have is `java.lang.AssertionError`.

`AssertionError` is great for signaling that a test has failed, but it doesn't go far enough. Each testing framework is therefore forced to fill the gap with custom subclasses of `AssertionError` or `RuntimeException` to provide a richer feature set to end users. The downside is that each framework has its **own** set of custom errors and exceptions, and this makes it a challenge for frameworks to interoperate.

For example, JUnit has long supported the notion of a _failed assumption_ via its `AssumptionViolatedException`, but assertion frameworks like AssertJ cannot integrate that feature without a direct dependency on JUnit. Furthermore, the status quo makes the work of IDEs and build tools more difficult than it should be.

## Proposal

The only real solution to this problem is to create a foundation that we can all build on!

Based on discussions with IDE and build tool developers from Eclipse, Gradle, and IntelliJ, the JUnit 5 team is working on a proposal for an open source project to provide a minimal common foundation for testing libraries on the JVM. The primary goal of the project is to enable testing frameworks like JUnit, TestNG, Spock, etc. and third-party assertion libraries like Hamcrest, AssertJ, etc. to use a common set of exceptions that IDEs and build tools can support in a consistent manner across all testing scenarios -- for example, for consistent handling of failed assertions and failed assumptions as well as visualization of test execution in IDEs and reports.

## Initial Implementation

We have begun with a small set of errors and exceptions that we consider to be common for all testing and assertion frameworks. In fact, these errors and exceptions are already used in [JUnit 5]. Please take a look at the project and let us know what you think.

## Javadocs

- [Latest release](http://ota4j-team.github.io/opentest4j/docs/current/api/)
- [Latest snapshot](http://ota4j-team.github.io/opentest4j/docs/snapshot/api/)

## Contributing

Contributions to the Open Test Alliance are both welcomed and appreciated. For specific
guidelines regarding contributions, please see [CONTRIBUTING.md] in the root directory of
the project. Those willing to use milestone or SNAPSHOT releases are encouraged to file
feature requests and bug reports using the project's
[issue tracker](https://github.com/ota4j-team/opentest4j/issues).

### Feedback is welcome!

What types of _errors_ and _exceptions_ should the OTA support?

What types of properties should such errors and exceptions have?

What additional functionality (e.g., interfaces, utility methods, etc.) should the OTA provide?

## Projects already contacted

We've already reached out to and asked for feedback from the maintainers of the following projects.

- Test NG
- Hamcrest
- AssertJ
- Spock
- Google Truth
- ScalaTest
- Eclipse
- IntelliJ
- Gradle
- Maven Surefire Plugin
- Allure Framework

# Installation

Release artifacts are deployed to [Maven Central].

Snapshot artifacts are deployed to Sonatype's [snapshots repository].

## Dependency Metadata

### Latest Release

- **Group ID**: `org.opentest4j`
- **Artifact ID**: `opentest4j`
- **Version**: `1.2.0`

See also: <http://search.maven.org/#search|ga|1|opentest4j/>

### Snapshots

- **Group ID**: `org.opentest4j`
- **Artifact ID**: `opentest4j`
- **Version**: `1.3.0-SNAPSHOT`

See also: <https://oss.sonatype.org/content/repositories/snapshots/org/opentest4j/opentest4j/>

[CONTRIBUTING.md]: https://github.com/ota4j-team/opentest4j/blob/master/CONTRIBUTING.md
[JUnit 5]: https://github.com/junit-team/junit5
[Maven Central]: http://search.maven.org/
[snapshots repository]: https://oss.sonatype.org/content/repositories/snapshots/
